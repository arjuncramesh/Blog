# Image Upload inside a server using Multer in Node.js and Express.js

I was thinking about a way to upload  profile pics into the Data base as part of my project and  i was having this idea of converting the image into a string using base64 and save it inside the db ,but it's not the proper or in otherwords not the correct way to do it. i did  some research and i figured it out that we should save the files inside your server, and we can do it with   the help of a  package called multer .This blog is about Image Upload Using Multer in Node.js and Express.js and i have made this blog as simple as possible.

## What is Multer?

Multer is a node.js middleware for handling multipart/form-data, which is primarily used for uploading files.

## steps

### 1)install the package

     npm i multer

### 2)Add multer in the file

    const multer = require(‘multer’);

### 3) Set up the location(location were the file has to be upload)

    For this u have to create a funtion

```js
        const storage = multer.diskStorage({
            destination:(req,file,cb)=>{       //destination is used by the application to know the location path  to store the images
                cb(null, 'uploads')     //upload is thefolder name
            },
            filename:(req,file,cb)=>{       //Filename determines how a file should be named in the folder.
            console.log(file)
            cb(null,Date.now()+ path.extname(file.originalname))        //null – because we aren’t showing an error.
            }
        });
```
### 4) file being filtered (since we are uploading an image the size and format should be filterd before uploading)

    Here we are creating a  Middleware whose funtion is to filter the file and also the above funtion(in the 3rd pont)that  we have created for setting up the location is being called in this funtion(filter funtion)
```js
  const imageUpload = multer({
  storage: storage,     //The  above funtion  storage   called here for setting up the location
  limits: {
    fileSize: 1000000    // restricting the file size upto a max of 1MB
  },
  fileFilter(req, file, cb) {        //method for filtering
    if (!file.originalname.match(/\.(png|jpg)$/)) {         // upload only png and jpg format
       return cb(new Error('Please upload a Image'))
     }
   cb(undefined, true)
}
})
```
### 5)call the middileware inside the api 

```js
app.post("/", imageUpload.single("image"), (req, res) => {  //imageUpload being the middileware and .single means a single image, you can use array etc as well
    res.send("done");
});
```

# Conclusion
I hope you have found this blog helpfull and have learned how to upload an image inside a server.After uploading the image store the path inside the database

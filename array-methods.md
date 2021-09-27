# Different Array Methods And Their Uses.
There are  a lot of methods which does not  necessarily known to all developers .However,code complexity can be reduced in order to make the code perfect with the help of applying methods in coding.The reason which makes it difficult for few people to comprehend the correct functionality  of the methods are due to these reasons, Have to speand a lot of time to read and understand ,Some explanations might be complicated, some methods performs some what similar  functions so it's difficult in understanding  the correct requirement of the methods etc...
        Here in this blog i've explained the array methods with simple definition and simple examples, please feel free to check it out.....

> ### 1) Symbol.iterator

This methods helps to iterate over the elements in the array.This property returns a function and when the function is called its gonna return an iterator.

#### Example:-

```c
    const a=[1,2,3,4];
    let b= a[Symbol.iterator]();
    console.log(b.next());
    console.log(b.next());
    console.log(b.next());
    console.log(b.next());
    console.log(b.next());
```

Result:-

```c
    { value: 1, done: false }
    { value: 2, done: false }
    { value: 3, done: false }
    { value: 4, done: false }
    { value: undefined, done: true }
```

value:-Element in the array

Done:-weather the loop is finished or not

<!-- //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////// -->

> ### 2) .concat()

This  method is used to merge two arrays, and returns a new array.

#### Example:-

```c
    const a=[1,1,2,3,];
    const b=[1,4,5,6];
    const c=a.concat(b);
    console.log(c);
```

Result:-

```c
[
    1, 1, 2, 3,
    1, 4, 5, 6
]
```

<!-- //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////// -->

> ### 3) .fill((value, start, end)

Here all the elments from the start point to the end point are replaced by the value ,the array length remains the same.

#### Example:-

```c
    const a = [0,1,2,3,4,5,6];
    console.log(a.fill(9,2,5));
```

Result:-

```c
    [
         0, 1, 9, 9,
         9, 5, 6
    ]
```

<!-- //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////// -->

> ### 4) .copyWithin(target, start, end)

In this method the elments from the start pont upto the end point are been copied to the target point, this method returns the same array without modifying the length .

#### Example:-

```c
    const a=[1,1,2,3,4,5,6];
    console.log(a.copyWithin(0, 3, 7));

```

Result:-

```c
    [
        3, 4, 5, 6,
        4, 5, 6
    ]
```

Here in this example the target point is 0(1),starting point 3(3) and ending point 7(it takes the value in the 6th index position ,so 6 )

<!-- //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////// -->

> ### 5) .entries()
>
> This method which returns a new array which has been iterated , the obeject with the array will be having a key value pair .The key is the index and the value is the element in the array.

#### Example:-

```c
    const a=["a","b","c"];
    const b=a.entries();
    console.log(b.next());
    console.log(b.next().value);
    console.log(b.next());
    console.log(b.next());
```

Result:-

```c
    { value: [ 0, 'a' ], done: false }
    [ 1, 'b' ]
    { value: [ 2, 'c' ], done: false }
    { value: undefined, done: true }
```

<!-- //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////// -->

> ### 6) .every()

It checks whether all elements in the array satisfy the condition inside the function.Returns a boolean

#### Example:-

```c
    const a = (currentValue) => currentValue < 4;
    const c = (currentValue) => currentValue < 10;

    const b=[1,2,3,4,5,6,7];
    console.log(b.every(a));
    console.log(b.every(c));
```

Result:-

```c
    false
    true
```

<!-- //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////// -->

> ### 7) .filter()

.filter method returns a new array of elements that have passed the condtion declared inside the filter.

#### Example:-

```c
    const a = [0,1,2,3,4,5,6];
    const c = (currentValue) => currentValue < 4;
    const d=a.filter(c);
    console.log(d);
```

Result:-

```c
    [ 0, 1, 2, 3 ]
```

<!-- //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////// -->

> ### 8) .find()

.find() returns the first element in the array that satisfies the condition that have been discribed inside the .find method.Returns undefined if elemnent satisfy the condition.

#### Example:-

```c
    const a = [0,1,2,3,4,5,6];
    const c = (currentValue) => currentValue < 4;
    const d=a.find(c);
    console.log(d);
```

Result:-

```c
   0
```

<!-- //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////// -->

> ### 9) .findIndex()
>
> Returns the index of the first element which satisfies the condition

#### Example:-

```c
    const a = [0,1,2,3,4,3,8,5,6];
    const c = (currentValue) => currentValue > 4;
    const d=a.findIndex(c);
    const f=a.find(c);

    console.log(d);
    console.log(f);




```

Result:-

```c
    6
    8
```
<!-- //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////// -->

>### 10) .flat()

.flat  returns a new array with  the sub array depth been decreased upto the specified value, wecan't increase the the depth using .flat method.
#### Example:-

```c
    const a= [0, 1, 2, [[[3, 4]]]];

    console.log(a.flat()); 

    console.log(a.flat(1));

    console.log(a.flat(2));

    console.log(a.flat(3));
```
Result:-

```c
    [ 0, 1, 2, [ [ 3, 4 ] ] ]
    [ 0, 1, 2, [ [ 3, 4 ] ] ]
    [ 0, 1, 2, [ 3, 4 ] ]
    [ 0, 1, 2, 3, 4 ]
```
<!-- //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////// -->

>### 11) .flatMap()

It is a combination of flat and map methods. Performs the operation on all the elements  inside the array and increase the depth of the new array

#### Example:-

```c
    let a = [0,1,2,3,4,3,8,5,6];
    console.log(a.flatMap(x => [[x * 2]]));
    console.log(a.flatMap(x => [[[x * 2]]]));
```

Result:-

```c
    [
        [ 0 ],  [ 2 ], 
        [ 4 ],  [ 6 ], 
        [ 8 ],  [ 6 ], 
        [ 16 ], [ 10 ],
         [ 12 ]
    ]
    [
        [ [ 0 ] ],  [ [ 2 ] ], 
        [ [ 4 ] ],  [ [ 6 ] ], 
        [ [ 8 ] ],  [ [ 6 ] ], 
        [ [ 16 ] ], [ [ 10 ] ],
        [ [ 12 ] ]
    ]
```

<!-- //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////// -->

>### 12) .forEach()

Perform an action over all the elements inside an array,and returns the element.

#### Example:-

```c
    const a = [0,1,2,3,4,3,8,5,6];
    let c=a.forEach(element => console.log(element*2));
```

Result:-

```c
    0
    2
    4
    6
    8
    6
    16
    10
    12
```

<!-- //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////// -->

>### 13) .includes()

Checks whether an element is present inside the array or not,returns true or false

#### Example:-

```c
    const a = [0,1,2,3,4,3,8,5,6];
    console.log(a.includes(10));
    console.log(a.includes(2));
```

Result:-

```c
    false
    true
```
<!-- //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////// -->
>### 14) .indexOf()

Returns the index where the element is present , return -1 if not found.

#### Example:-

```c
    const a = [0,1,2,3,4,3,8,5,6];
    console.log(a.indexOf(10));
    console.log(a.indexOf(2));
```

Result:-

```c
   -1
    2   
```
<!-- //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////// -->
>### 15) Array.isArray()

checks whether an array or not, returns true or false.

#### Example:-

```c
    const a = [0,1,2,3,4,3,8,5,6];
    const car = {type:"Fiat", model:"500", color:"white"};
    console.log(Array.isArray(a));
    console.log(Array.isArray(car));
```

Result:-

```c
    true
    false
```
<!-- //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////// -->
>### 16) .join()

Return a new string with the elements in the array  which are separated specified separator.

#### Example:-

```c
    const a = [0,1,2,3,4,3,8,5,6];
    console.log(a.join());
    console.log(a.join('+'));
    console.log(a.join('-'));
```

Result:-

```c
    0,1,2,3,4,3,8,5,6
    0+1+2+3+4+3+8+5+6
    0-1-2-3-4-3-8-5-6
```
<!-- //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////// -->
>### 17) .keys()

Act  kind of  an Iterator function, which return the index of the key.

#### Example:-

```c
    const array1 = ['a', 'b', 'c'];
    const b = array1.keys();
    console.log(b.next());
    console.log(b.next());
    console.log(b.next());
    console.log(b.next());
```

Result:-

```c
    { value: 0, done: false }
    { value: 1, done: false }       
    { value: 2, done: false }       
    { value: undefined, done: true }
```
<!-- //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////// -->
>### 18) .lastIndexOf()

Returns the last found index of the  searched element in the array,returns -1 is not found.

#### Example:-

```c
   const a=[1,2,3,4,5,1,1,4,5,6,6]
   console.log(a.lastIndexOf(1));
   console.log(a.lastIndexOf(0));
```

Result:-

```c
     6
    -1
```
<!-- //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////// -->
>### 19) .map()

Performs the operation over all the elements in the array and returns a new array. 

#### Example:-

```c
    const a = [0,1,2,3,4,];
    let c=a.map(element => (element*2));
    console.log(c);

```

Result:-

```c
    [ 0, 2, 4, 6, 8 ]
```
<!-- //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////// -->
>### 20) Array.of(element)

creates an array.

#### Example:-

```c
    const a= Array.of(0,1,2,3,4);
    const b= Array.of("cat","dog","snake");
    console.log(a);
    console.log(b);
```

Result:-

```c
    [ 0, 1, 2, 3, 4 ]
    [ 'cat', 'dog', 'snake' ]
```
<!-- //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////// -->
>### 21) .pop()

 removes and return the last element.Changes the length of the array.

#### Example:-

```c
    const a= Array.of(0,1,2,3,4);
    console.log(a);
    console.log(a.pop());
    console.log(a.pop());
    console.log(a.pop());
    console.log(a.pop());
    console.log(a.pop());

```

Result:-

```c
    [ 0, 1, 2, 3, 4 ]
    4
    3
    2
    1
    0
```
<!-- //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////// -->
>### 22) .push()

Add a new element to the end of the array. Changes the length of array.

#### Example:-

```c
   const a= Array.of(0,1,2,3,4);
    console.log(a);
    a.push("a");
    a.push("b");
    console.log(a);

```

Result:-

```c
[ 0, 1, 2, 3, 4 ]
[
  0, 1,   2,   3,
  4, 'a', 'b'
]
```
<!-- //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////// -->
>### 23) .reduce()

Takes two elements and perform an action, the action is again  performed with the result   and the next element .This process is repeated until the last element has been reached .   

#### Example:-

```c
    const a = [1, 2, 3, 4];
    const res = (previousValue, currentValue) => previousValue + currentValue;
    console.log(a.reduce(res));
```

Result:-

```c
   10
```
<!-- //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////// -->
>### 24) .reduceRight()

Takes two  elements the last position  and perform an action, the action is again  performed with the result   and the next element .This process is repeated until the first element has been reached . Same as reduce but in reduce its left to right how the operation is performed  but in reduce right its form right to left 

#### Example:-

```c
    const a = [10,4,2,1];
    const res = (previousValue, currentValue) => previousValue-currentValue;
    console.log(a.reduce(res));
    console.log(a.reduceRight(res));
```

Result:-

```c
     3
    -15
```
<!-- //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////// -->
>### 25) .reverse()

Reverse the array,The first element becomes the last element and vice versa. 

#### Example:-

```c
    const a = [0,1,2,3,4,5]
    console.log(a.reverse());
```

Result:-

```c
   [ 5, 4, 3, 2, 1, 0 ]
```
<!-- //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////// -->
>### 26) .shift()

Returns the first element in the array.Changes the length of the array.

#### Example:-

```c
    const a = [0,1,2,3,4,5]
    console.log(a.shift());
    console.log(a.shift());

```

Result:-

```c
    0
    1
```
<!-- //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////// -->
>### 27) .slice(start,end)
Slice the array from the start index to the end index mentioned in the slice method.The orginal array remains the same.
#### Example:-

```c
    const a = [0,1,2,3,4,5]
    console.log(a.slice(1,3));
    console.log(a);
```

Result:-

```c
   [ 1, 2 ]
   [ 0, 1, 2, 3, 4, 5 ]
```
<!-- //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////// -->
>### 28) .some()

Checks whether at least one element satisfies the condition.Return true or false.   

#### Example:-

```c
    const a = [1, 2, 3, 4, 5];
    const greater= (element) => element>4;
    const greatest= (element) => element>7;

    console.log(a.some(greater));
    console.log(a.some(greatest));
```

Result:-

```c
   true
   false
```
<!-- //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////// -->
>### 29)  Array.sort()

The elements are sorted in a special manner.

#### Example:-

```c
    const a = ["dog","cat","lion","snake"];

    console.log(a.sort());
```

Result:-

```c
   [ 'cat', 'dog', 'lion', 'snake' ]
```
The sorting is done in such a manner that the elements first letters are considerd.C comes first then d the l the s, since such a result.
<!-- //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////// -->
>### 30) splice(start, deleteCount, item)
In splice the item is added to the start index .The deletecount index determines the element to be deleted.
#### Example:-

```c
    const a = ["dog","cat","lion","snake"];

    a.splice(1,0,'crow')
    console.log(a); 
```

Result:-

```c
   [ 'dog', 'crow', 'cat', 'lion', 'snake' ]
```
<!-- //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////// -->
>### 31) .toString()

Converts the array to a string  

#### Example:-

```c
    const a = ["dog","cat","lion","snake"];

    const b=a.toString()
    console.log(b);

```
Result:-

```c
   dog,cat,lion,snake
```
<!-- //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////// -->
>### 32) .unshift()

Add elements to start of the array.  changes the length of the array.

#### Example:-

```c
    const a = ["dog","cat","lion","snake"];

    a.unshift(1,2,3,4);
    console.log(a);
```

Result:-

```c
   [ 1, 2, 3, 4, 'dog', 'cat', 'lion', 'snake' ]
```
<!-- //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////// -->
>### 33) .values()

Act as an iterator funtion that returns each value in the array.

#### Example:-

```c
    const a = ["dog","cat","lion","snake"];
    let b=a.values();
    console.log(b.next().value);
    console.log(b.next().value);
    console.log(b.next().value);
```

Result:-

```c
    dog
    cat
    lion
```
<!-- //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////// -->

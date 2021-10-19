## Destructuring Assignment

### Introduction
Today I continued to learn ES6 on FreeCodeCamp and the destructuring assignment lesson literally just blew my mind.
I never thought extracting values of an object could be so clean and easy. This is how I extract the values of an object 
before:

```
    // object declaration
    var obj = {name : Alex, age : 14};
    // extracting the values
    var objName = obj.name;
    var objAge = obj.age;
```

This is how I extract the values of an object after i learned destructing assignment:

```
    //object declaration
    var obj = {name : Alex, age : 14};
    // extracting by destructing assignment
    const {name:objName, age:objAge} = obj;
```
voila! The values from the object is extracted with just single line of code. Of course you can extract a specific value 
from the object, we just have to specify which value of the property we want in the curly bracket. If we didnt specified the 
name of the variable which the values store in, it will use the name of the property as the variable name by default.

### Striving deeper
This is it? No. Destructuring assignment can also be used to unpack specific values from the object into a function.
I will present my understanding with following example.

###### Consider this simple object with multiple properties
```
    const obj = {
        median:40,
        max:90,
        min:20,
        freq:100
    };
```
Before i learn this lesson, I will assign the min and max values of the object into a variable first then only I will insert them
into the function as arguments. Like this:

```
    const max = obj.max;
    const min = obj.min;
    console.log((max,min)=>(max+min)/2);
```
But with destructuring assignment, I can just do this and obtain the same result

```
    console.log(({max,min})=>(max+min)/2);
```
However, I still prefer to do this to prevent any misassignment of object property

```
    const {min,max} = obj;
    console.log((min,max)=>(max+min)/2);
```
### Storing leftover values into array using rest parameter
Well, quick recap on myself.
1. Rest parameter can only be used as the last argument
2. Rest parameter will pack multiple values or element into an array

So, by doing this, I can store the left over values of an object for future use after I used Destructuring assignment.

```
    const {min,max,...leftOver} = obj;
    // leftover will pointing to an array storing [40,100]
```

### Destructuring assignment on array
I almost forget this part when I was writing this note. In short, Destructuring assignment works similarly on array datatype
With this, we can pick desired element in an array and assign them to a new variable, which can be packed into a new array or other purposes. 
This is different from using the spread parameter that will unpack all the elements of an array.

By incorporating destructuring assignment with the rest parameter, we can slice an array into 2 will minimal effort.

```
    const [a,b,...arr] = [1,2,3,4,5,6];
    arr1 = [a,b]
    //arr will store [3,4,5,6]
```
Swapping of the values of 2 variables also can be made simple

```
    var x = 1, y = 5;
    [y,x] = [x,y];
```

*Edited 19/10/2021*
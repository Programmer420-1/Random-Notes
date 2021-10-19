### This is the important lesson learnt from JavaScript Course (FreeCodeCamp)

#### Recursion
When using recursion, a BASE CASE must be declared. Otherwise it will cause RangeError, that is when the
call stack is overloaded with pending functions, causing the stack to overflow. In JavaScript recursion,
consecutive functions call are stacked on top of each other when being called, thus when invoking the
function, the last function called will be invoked first. __[The first card in, the last card out]__

```
       *      - the last functions called (the first functions invoked)
      * *     - the forth functions called (the second functions invoked)
     * * *    - the third functions called (the third functions invoked)
    * * * *   - the second functions called (the forth functions invoked)
   * * * * *  - the first functions called (the last functions invoked)
```
For example, below is an recursive function that will return an array of numbers of the first n numbers from 1 __inclusively__:

```
function countup(n){
    if (n <= 0){
        return [] //base case, an empty array is return to be filled by last function called.
    }
    else {
        var arr = countup(n-1); //storing a function call into a variable
        arr.push(n); //method to fill the array to the end of array
        return arr; //returning the array to last function call
    }
}
```

visual reference please refer to https://drive.google.com/file/d/1m2L-KAX8qoMJqO9v6LQBxEEzbQvrpYgT/view?usp=sharing 

As the first card in last card out rule applies, the array return will be [1,2,3,4,5] instead of [5,4,3,2,1]. Thus to inverse the sequence, we just have to
use arr.unshift(n) instead of arr.push(n)

*Date Edited: 18/10/2021*
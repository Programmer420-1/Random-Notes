## Promise
### Introduction
Today I decided to take a break from Java and learn JavaScript again. Still, I use the same source, which is FreeCodeCamp, and today I managed to complete the ES6 course. Even though I learnt quite a few programming language before but this is the first time I encounter with Promise. So the following will be what I have understand from the lesson. Correct me if I am wrong :)
#
### Introduction to Promise
Promise in JavaScript is literally making a promise to do something in a program. A promise can have 3 states, which are `pending`, ` resolved` and `rejected`. A promise is always used to run a task that required an unknown amount of time to complete. A promise is always used with a few other methods from the same class to become functional.
<br><br>
To create a promise, `new` keyword is used as Promise() is a constructor. The constructor takes in a functional as its argument and the function has to take 2 arguments, which are `resolve` and `reject`
```js
    const aPromise = new Promise((resolve,reject)=>{code block});
```
If the code block part is left empty, the promise will be in pending state forever as the promise can't tell itself whether it is resolved or rejected. Thus we need to include some condition in order to escape frompending state.
```js
    const aPromise  = new Promise((resolve,reject)=>{
        if (condition){
            resolve("Resolved Message");
        }
        else{
            reject("Rejected Message");
        }
    });
```
#
### Promise methods
Promise has a few methods that is often incorporated with the Promise object. They are `.then()`,` .catch()`,` .finally()` methods.
Three of them are usually accepting functions as argument to carry out consecutive task after the promise state is returned(either resolved or rejected). 
<br><br>
#### ` .then()` Method
`.then()` method is used when you want to carry out next task after a promise status is returned. This method can also be chained to carry out a series of task. This is very useful when we don't know the exact amount of time needed to execute the piece of code in the exam, Promise will make this kind of task asynchronous.
```js
    //not chained promise method
    const aPromise = new Promise((resolve,reject)=>{code block}).then(expression);
    //chained promise method
    const aPromise = new Promise((resolve,reject)=>{code block}).then().then().then();
```
<br><br>
#### ` .catch()` Method
` .catch()` method is used when we want to catch the exception during our code execution in Promise. The method will accept the exception returned from the Promise and perform Exception Handling.

<br><br>
#### ` .finally()` Method
` .finally()` method is used when we want to run an execution no matter the outcomes produced from the Promise. Calling the `.finally()` method is the same as calling `.then()` and `.catch()` except that it does not accept any arguments. The method is usually being used to clean up the code after execution. For example, clearing the cache after a Promise operation is completed regardless of it is successful or failed.
```js
    const aPromise = new Promise((resolve,reject) => {
        let a = 1+1;
        if(a == 2){
            resolve("Successful Operation");
        }  
        else{
            reject("Failed Operation");
        }
    });
    
    aPromise.then(message => {
        console.log(message)
    }).catch(message => {
        console.log(message)
    }).finally(() => {
        console.log("This block executes Finally")
    });
```
Output:
```
    Successful Operation
    This block executes Finally
```
<br><br>
#### ` .all()` Method
`.all()` method is a little different from the previous 3 methods. `.all()` is used when we want to execute multiple promises at the same time. To use this we use simply type in `Promise.all();` and we passed in an array of promises as the argument. The method will then execute all promises at the same time. This method will also wait for the other promises to finish before executing `.then()` or `.catch()` or `.finally()`.
```js
    const Promise1 = new Promise((resolve,reject)=>{
        resolve("Promise 1 output");
    });
    
    const Promise2 = new Promise((resolve,reject)=>{
        resolve("Promise 2 output");
    });
    
    const Promise3 = new Promise((resolve,reject)=>{
        resolve("Promise 3 output");
    });
    
    const Promise4 = new Promise((resolve,reject)=>{
        resolve("Promise 4 output");
    });
    
    Promise.all([
       Promise1,
       Promise2,
       Promise3,
       Promise4
    ]).then((messages) => {
        console.log(messages);
    });
```
Output:
```
    [ 'Promise 1 output', 'Promise 2 output', 'Promise 3 output', 'Promise 4 output' ]
```
Note that the message from all of the promises are outputted in the form of an array instead of being printed seperately to the console. This is because the `.all()` method will wait for all the promises to complete before moving to next method.
<br><br>
#### ` .race()` Method
`.race()` method is used when we want to execute multiple promises at the same time but only get the resolve from the first promise to complete. This method will execute `.then()` or `.catch()` or `.finally()` that comes after the method as soon as there is one promise completed its operation. Hence, there will only be one message being outputted.
```js
    const Promise1 = new Promise((resolve,reject)=>{
        resolve("Promise 1 output");
    });
    
    const Promise2 = new Promise((resolve,reject)=>{
        resolve("Promise 2 output");
    });
    
    const Promise3 = new Promise((resolve,reject)=>{
        resolve("Promise 3 output");
    });
    
    const Promise4 = new Promise((resolve,reject)=>{
        resolve("Promise 4 output");
    });
    
    Promise.race([
       Promise1,
       Promise2,
       Promise3,
       Promise4
    ]).then((message) => {
        console.log(message);
    });
```
Output:
```
    Promise 1 output
```
As we can see, only the promise that complete first will display its message using `.then()` method which comes after  `.race()` and if we chain another `.then()` method after the first like below,
```js
    Promise.race([
       Promise1,
       Promise2,
       Promise3,
       Promise4
    ]).then((message) => {
        console.log(message);
    }).then((message) => {
        console.log(message);
    });
```
The output will be
```
    Promise 1 output
    undefined
```
<br><br>
*Edited 25/3/2022*








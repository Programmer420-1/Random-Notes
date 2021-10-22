## Promise
### Introduction
Today I decided to take a break from Java and learn JavaScript again. Still, I use the same source, which is FreeCodeCamp, and today I managed to complete the ES6 course. Even though I learnt quite a few programming language before but this is the first time I encounter with Promise. So the following will be what I have understand from the lesson. Correct me if I am wrong :)
#
### Introduction to Promise
Promise in JavaScript is literally making a promise to do something in a program. A promise can have 3 states, which are `pending`, ` resolved` and `rejected`. A promise is always used to run a task that required an unknown amount of time to complete. A promise is always used with a few other methods from the same class to become functional.
<br><br>
To create a promise, `new` keyword is used as Promise() is a constructor. The constructor takes in a functional as its argument and the function has to take 2 arguments, which are `resolve` and `reject`
```
    const aPromise = new Promise((resolve,reject)=>{code block});
```
If the code block part is left empty, the promise will be in pending state forever as the promise can't tell itself whether it is resolved or rejected. Thus we need to include some condition in order to escape frompending state.
```
    const aPromise  = new Promise((resolve,reject)=>{
        if (condition):
            resolve("Resolved Message");
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
```
    //not chained promise method
    const aPromise = new Promise((resolve,reject)=>{code block}).then(expression);
    //chained promise method
    const aPromise = new Promise((resolve,reject)=>{code block}).then().then.then();
```
<br><br>
#### ` .catch()` Method
` .catch()` method is used when we want to catch the exception during our code execution in Promise. The method will accept the exception returned from the Promise and perform Exception Handling.








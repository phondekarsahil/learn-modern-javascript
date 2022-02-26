# Modern JavaScript

## Intro & Setup

* This project is all about JavaScript for websites.
* We can take a static website but with just HTML and CSS and with just a few lines of JavaScript we can breathe all sorts of life into it and that's going to open up so many doors for you when you creating these new websites.
* And what's more when you're comfortable with working with JavaScript in the browser you can start to use it for backend development to run on a server because JavaScript can be used for front-end development and backend development thanks to a little thing called `nodejs`.

## What is a server?

* When we visit a web site in a browser what we typically do is type in the address into the address bar press ENTER and then that sends a request to a web server.
* And a web server is just some other computer out there on the web somewhere and it's containing all of the different files that make up this particular website.
* So when we press ENTER and we send that request, the web server is going to receive that request and it's going to say ok I'll send you a response to the browser and that response is going to contain the HTML CSS and JavaScript that make up this website so the browser receives that response and then it shows the website in the browser and we can see it.
* So that's the way this request and response cycle works now since our files when we make then when we make our projects will be stored on our own computer rather than some remote computer because we don't want to keep up loading the files to the web somewhere to preview them so they're going to be on our own computer we'll need a way for our computer to serve the files to the browser as if we were visiting a real web site now to do that we use what's known as a local development server.
* It allows our computer to act as a server for our websites so we can type in a specific local address into a browser hit enter and that's going to tell our computer to serve up our website files our HTML CSS and JavaScript to the browser so that we can view them and the address that we go to over here is called localhost which just means we're using a local server on our computer.

## Where do we add JavaScript to an HTML page?

* Well we can add it anywhere between the `head` tags or anywhere between the `body` tags. 
* Now placing the script inside a `head`, that's absolutely fine, you can do that but in some cases it's going to cause some loading issues so 99% of the time if you're adding javascript to a page I would do it not here but instead at the ***bottom of the body tag*** just before the closing body tag.

## Variables and Constants

* one of the most fundamental things in JavaScript is this notion of variables and what variables do is give us a way to store a value like a name or a number or an email and then use that value whenever we want to later on in the file
* There's a few different ways we can make a variable the first way to create one is by using the `let` keyword
```js
let age = 12;
console.log(age); // prints 12
```
* So this let keyword creates us a variable and if we want to override the value of those variables later on we can do so
```js
age = 30;
console.log(age); // prints 30
```
* For creating constants we use `const`
```js
const pi = 3.14;
``` 
* If we don't want this value to be overridden by mistake any point we declare it as `const`
* There is another older keyword that we can use to create variables too and that is the `var`.
```js
var year = 2022;
```
* Also we can override the value of variables declared using `var`.
* When we're using modern JavaScript techniques like `let` and `const` and other things in the future they might not work in 100% of browsers out there old browsers like Internet Explorer 11 and things like that they don't support a lot of the modern features.

## Datatypes
* In JavaScript there are 7 different data types we can work with, they're all listed here.

    |No.|Datatype   | Examples                                          |
    |---|-----------|---------------------------------------------------|
    | 1 | Number    | 1,2,3, 100, 3.14                                  |
    | 2 | String    | 'hello, world', "hello, world"                    |
    | 3 | Boolean   | true / false                                      |
    | 4 | Null      | Explicitly set a variable with no value           |
    | 5 | Undefined | For variables that have not yet been defined      |
    | 6 | Object    | Arrays, Object Literals, Functions, Dates etc     |
    | 7 | Symbol    | Used with Objects                                 |

*  `null` over here this is a way in which we can explicitly say that a variable has no value.
* Now it's closely related to undefined here but the difference is undefined is a type that's given to variables automatically by the browser that have not yet been defined.
* So these are both empty values, but `null` we explicitly set to a variable and `undefined` automatically given to variables when they're not yet defined.
* Finally symbols they are a new addition to the JavaScript language which are closely linked to objects.
* We can change the type of variables declared using `let` or `var` at any point in the code and for that reason javascript is known as a `loosely typed language`

## Control Flow (Loops and Conditionals)

* A `loop` is a type of control flow in JavaScript
* Also sometimes we need to only run some code when a condition is true and this is known as a `conditional statement`
* So these two different concepts of looping and conditionals they are collectively known as `control flow` in JavaScript because we're using them to control the flow of our code or application whether that be using a loop to repeat a section of code or to conditionally run a section of code based on a certain condition.
* When we open the curly braces and we close the curly braces that is what is known as a `code block`
```js
{
    //code block
}
```
* It's just a section of code that we're kind of sectioning off
* `for loops`: 
```js
for (statement 1; statement 2; statement 3) {
  // code block to be executed
}

/*
Statement 1: first thing right here this is an initialization variable
Statement 2: second thing is a condition. This is going to evaluate to either true or false. If this condition is true then we're going to execute the code that's inside this code block if it's false then we're not going.
Statement 3: third thing over here this is a final expression and this is going to execute every time at the end of the code block
*/
```
* `if statements`
* `break` and `continue`: 
    
    1. `break` keyword means now I just want to break completely from the loop ignore all this stuff at the top and carry on with the rest of the code down.
    2. `continue` is used when you want to now ignore the rest of the code inside the code block for this loop. But still you want to continue with the loop itself, so it will go back up to the top and go to the next iteration.

* `switch statements`

## Scope of variable

* Scope of a variable means the area in which a variable value is relevant.
* When we define a variable using `let` or `const` in the root of the document, meaning not inside any code block, it's in the root of the document, then that will have `global scope` and that means it can be accessed anywhere in the file.
* We are allowed to do declare a variable with same name as a global variable declared using `let` inside a code block even though it's got the same name.
```js
let age = 40;
{
    let age = 30;
    console.log(age) // 30
}
console.log(age) // 40
```
* In above eg, When we redefine the variable, what it does is recreate this variable but it gives it a local scope. Now we can only access this version of age inside this code block.
* Once we define a constant we can't change them. But the same rules of scope apply to `const` as they do to let variables. 
* So this idea of block scope is one of the main advantages of using `let` in `const` instead of the older `var` keyword.
* When we make a variable using `var` it ignores block scope

## Functions

* Functions are probably one of the main building blocks in pretty much any programming language that you come across. 
* They fall under the `object` type in our data type list.
* What functions allow us to do is define a block of code which we can call and execute whenever we want.
```js
// declaring functions
function add(a, b) {
    return a+b;
}
// function expressions
const calculate1 = (a, b) => {
    return a+b;
}
const calculate2 = function(){
    return a+b
}
```
* `Function expression` - When we store a function inside a variable it is called function expression.
* `Function declaration` - When we do not store a function inside a variable it is called function declaration.
* Most of the time these two different ways of creating functions they behave the same way but there is a subtle difference when it comes to something called `hoisting` in JavaScript.
* Now `hoisting` is a term that loosely describes how our functions are effectively hoisted to the top of a file before the rest of our JavaScript actually runs.
* So in essence they're all declared before the rest of our job script and it does this with function declarations but it doesn't do this with function expressions.
```js
greet(); // prints "Hello"

function greet(){
    console.log("hello");
}
```
* In above example the function is hoisted hence we can use it before its declaration.
* So hoisting works with function declarations but it doesn't work with function expressions.
```js
speak() // throws error - speak is not defined
const speak = function(){
    console.log("Hello")
}
```
* This might seem like a good idea to use this `function declaration` instead of `function expression` at first but actually it's not such a good idea as it doesn't enforce a good coding practice.
* You should declare something first and then use it to keep a logical flow to your code and if you don't do that you could end up with a mismatch of functions and calls all over the place. 
* Therefore I prefer most of the time to use `function expressions` like this which are not hoisted so that we have to define our functions first at the top before we use them.
* Arguments / Function parameters - When we pass in a value to a function it is known as an argument or Function parameters.
```js
const speak = function(name){
    console.log(`Hello ${name}`)
};
speak("John");
```
* `Arrow Functions`: Arrow functions are a more modern addition to the JavaScript language and they offer us a cleaner and shorter way to write functions. 
```js
const calc = (a, b) => {
    return a+b;
}
// without return statment
const calc = (a, b) => a+b;
```
* `methods and functions`: methods and functions are kind of synonymous with one another because they do the same thing. What distinguishes methods is the way that we invoke them and where they are defined.
```js
function hello(){
    return "Hello";
};
const message = hello();
console.log(message); // Hello
```
* In above example we just invoke the function like, the function name and then parentheses. Now when we use a method the method is invoked using dot notation.
* `Callback function`: We can also pass in a function as an argument and when we do this the function we pass in is called a callback function
* In general, we pass a function into something another function as an argument and at some point in that other function that callback function will probably be called and may be passed a value which we can take in.

## Objects
* The best way to understand what an object in JavaScript is is to compare it with a real-life object so objects in real life they have properties and they have things they can do right so for example a phone is a real object and it has properties it could have a color size a model etc but it also has things it can do it can ring take a picture and play music.
* JavaScript objects are quite similar they both have properties and they both have things they can do but in JavaScript they're called methods which have functions
* We can create individual objects using what's known as `object literal notation`
```js
let user = {
    name: 'crystal',
    age: '30',
    login: function(){
        console.log("The user logged in");
    }
    logData: function(){
        console.log(this.name);
    }
}
user.logData()
```
* In above example, when we invoke that `logData` method, javascript sets the value of the `this` keyword to the object that the method was used on.
* Now inside the function therefore we can use that this keyword to refer to the object itself.
* Notice that we've used a regular function right here to define this function. We have not used an arrow function and that was intentional because arrow functions work differently with the `this` keyword
* Different Ways to declate function property on an object: 
```js
let user = {
    ...
    logData1: function(){
        console.log(this.name);
    }, // method 1
    logData1() {
        console.log(this.name);
    } // method 2
}
```
## Math Object

* JavaScript has a whole bunch of ready-made objects built into the language which we can use out of the box and one of those is the math object.
* This math object has got several properties and methods all pre-made and bundled into it.
```js
console.log(Math.PI);
console.log(Math.round(7.7));
```

## Primitive & Reference Types

* Primitive & Reference Types

    |Primitive Types | Reference Types |
    |----------------|-----------------|
    | numbers | all types of objects |
    | strings | object literals |
    | Booleans | arrays |
    | null | functions |
    | undefined | dates |
    | symbols | all other objects |
    |  |  |

* What is the difference between primitive types and reference types?
* Well it's all to do with how they are stored and used in memory.
* So when we create a primitive value like a new string a new number or a boolean and we assign it to a variable that value is stored on something called the stack.
        
    |stack|
    |-----|
    | - |
    | - |
    | true |
    | 100 |
    | 'hello' |

* The `stack` is just a stack of different values in memory and they can be accessed pretty quickly when we need to use one.
* But the space inside this stack is quite limited so when we create a reference type like an object literal or an array that is stored not on a stack but on what is known as the `heap`.
* The `heap` has more space available so it can hold bigger and more complex types like objects and arrays but it's a bit slower.
* So `primitive types` are stored on the `stack` which is a bit quicker and `reference types` are stored on the `heap`.
* When we store a primitive value in a `variable` it adds that value to the stack and it locks the variable name to it as an `accessor` to that value.
* When we store a reference type in a `variable` like an object it adds the object to the `heap` and then it adds a `pointer` to that object on the `stack`. Also it locks that variable name to the pointer, so that we can access that pointer and eventually the object from the heap.
* Hence when we create a copy of a primitive variable, it does not create a new copy and add it to the `heap`, it just adds a the pointer to the `stack` referencing the original object.
```js
let user1 = { name:"Sahil", age: 25 };
let user2 = user1;
user1 = { name:"Tom", age: 54 }
console.log(user1) // { name:"Tom", age: 54 }
console.log(user2) // { name:"Tom", age: 54 }
``` 
* In above example the object is stored in a `heap` and `user1` variable contains the pointer to that object. When we say `user2 = user1` we are storing the pointer to the same object in `user2` variable. Hence both `user1` and `user2` point to same object. Hence when we change `user1` `user2` is also changed. 
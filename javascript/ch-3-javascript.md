# Functions & variable scope

## What is a function? 

A **function** is like a reusable machine in your code.
You give it some ingredients (called **parameters**), it does something with them, and it may give you something back (called the **return value**).

You create it once, then use it many times.

So it's like ***automation*** or a template. 

## Why Use Functions?
- Avoid repeating code
- Make code easier to read and maintain
- Break complex problems into smaller step

## Function Syntax 

### Traditional Syntax

    function sayHello(name) {
    alert("Hello, " + name);
    }

- `function` = tells JavaScript you’re creating a function
- sayHello = the name of the function
- (name) = the parameter (like a placeholder)
- { ... } = the body where the code runs

For example, think of it like a coffee machine:

    function makeCoffee(typeOfCoffee) {
    return "Here is your " + typeOfCoffee;
    }

Then you can say:

    let cup = makeCoffee("Latte");
    alert(cup); // "Here is your Latte"


### Function Expression (Assigned to a variable)

    var greet = function(name) {
    alert("Hi, " + name);
    }

This does the same thing, but it stores the function inside a variable.  
This is useful when you want to pass functions around like objects.

## Calling a function 

Once you’ve defined a function, you can use it by calling it:

    sayHello("Lía");

If your function returns something:

    function add(a, b) {
    return a + b;
    }

    let result = add(3, 5);
    alert(result); // shows 8

Another example: 

    var greet = function(name, country) {
    alert("Hi " + name + " from " + country);
    };

    greet("Lía", "Ecuador");

## Function that returns something

It gives something back instead of just showing it. 

    var average = function(a, b, c) {
    return (a + b + c) / 3;
    };

    let avg = average(10, 20, 30);
    alert(avg); // 20

It's like a calculator, where you enter numbers, and it gives/shows you the answer. 


## Passing a function as a parameter

A function can be given another function. 

Example: 

    var now = function () {
    return Date();
    };

    var show = function (fn) {
    alert("Today is: " + fn());
    };

    show(now);

### Anonymous Function (no name)

It's like an instant helper with no name yet.  

You can even define the helper function right inside the call:

    show(function () {
    return Date();
    });






## Variable Scope

> Understanding variable scope is essential to use functions correctly, avoid bugs, and write clean code.

### What is scope?

Scope means where a variable exists in your code, where you can access or use it.  

There are two main types of scope:

#### Global Scope
- Variables declared outside of any function.
- You can access them anywhere in your code (even inside functions).

Example: 

    var greeting = 'hello';

    var sayHi = function () {
    console.log("Inside function: " + greeting); // ✅ works
    };

    sayHi();
    console.log("Outside function: " + greeting);   // ✅ also works

Both lines work because greeting is global.

#### Local Scope
- Variables declared inside a function.
- You can only use them inside that function

Example: 

    var sayHi = function () {
    var greeting = 'hello';
    console.log("Inside function: " + greeting); // ✅ works
    };

    sayHi();
    console.log("Outside function: " + greeting);   // ❌ Error: greeting is not defined

You’ll get an error in the second console.log because greeting only exists inside the function.

#### Exception: Missing var (or let/const)
> If you forget to write var, let, or const inside a function, JavaScript creates a global variable by mistake. 

    var sayHi = function () {
    message = "HELLO"; // ❗No var = becomes global!
    console.log("Inside function: " + message); // ✅ works
    };

    sayHi();
    console.log("Outside function: " + message);   // ✅ also works — but risky!

This is dangerous. Always use let, const, or var to avoid accidental globals.

#### Overlapping scope (shadowing)

You can have a **global and a local variable** with the same name.
Inside the function, JavaScript uses the local one.

    var word = 'hello';

    var sayBye = function () {
    var word = 'goodbye'; // same name, but only inside function
    console.log("Inside function: " + word); // "goodbye"
    };

    sayBye();
    console.log("Outside function: " + word);   // "hello"

> JavaScript picks the **closest variable in scope**. Local **variables override global ones** inside their function.


## Summary 

| Type of Variable     | Where You Can Use It       | Where It's Declared                      | Notes                                   |
|----------------------|----------------------------|-------------------------------------------|-----------------------------------------|
| **Global variable**   | Everywhere                 | Outside functions                         | Used everywhere                         |
| **Local variable**    | Only inside the function   | Inside function using `var`, `let`, or `const` | Safer                                  |
| **Accidental global** | Everywhere                 | Inside function **without** `var/let/const` | ❗ Avoid this                            |
| **Shadowed variable** | Inside function            | Inside function                           | Overrides the global version temporarily |


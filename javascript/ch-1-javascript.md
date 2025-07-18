# JavaScript

## What is JS? 

JS is a programming language that lets webstites respond to what the user does. (The personality of a website)

> HTML = skeleton of the body. 
>
> CSS = clothes and design 
>
> JavaScipt = the brain and the muscles

### Event (ACTION)

- An event is something the user does or something that happens. For example clicking a button. 

- Events = triggers 

### Behavior (REACTION)

- Behaviors are reactions of the event. 
- Bahaviors = actions 

## Add JS 

Inside HTML using the script tag or linked to an external .js file. 

	<script>
  		alert("Hello!");
	</script>
or 

	<script src="code.js"></script>

## Development tools 

### Useful Extensions

1. Live Server 
2. ESLint (like a spell-checker for JS)
3. Debugger for Chrome (to see what's going on)

### Debugger 
**Breakpoint**: "Pause here when running, I want to check things."

And you'll do it like a stop motion frame by frame. Or in the case of JS function by function. 

## Terms 

### Loop
**Loop**: Repeat an action x amount of times. 

--> Example: A loop that counts from 1 to 5

	for (let i = 1; i <= 5; i++) {
		console.log("Envelope " + i + " has a sticker!");
	}

- i = 1 → start at envelope 1
- i <= 5 → do it until envelope 5
- i++ → go to the next one

Envelope 1 has a sticker!  
Envelope 2 has a sticker!  
...  
Envelope 5 has a sticker!  


### Variable 

A **variable** is like a labeled box where you want to store something. You can nme the box anything and put whatever you want in it: number, word, etc. 

**Example 1:**  

	let name = "Lía"; 

(guestName is a box with my name on it)

Which can read: "Let me create a box called name, and inside it, I’ll put the value "Lía""

**Example 2:**  

	let stickers = 10; (stickers is a box with the number 10)

>For syntax, you have labelOfTheBox = "What you put inside the box"

💡 Variable naming
You can use lowercase or camelCase. 


### Print 

**Print** is to show the result on screen, usually in the console. 

With JS, you can't see what's happening without asking, that's why you *print* - to check what's happening. 

	console.log("Hello, Lía!");


**print / console.log()** > Show output to the developer (not to users)
The **Output** goes to the developer console, not the web page. 

### Debugging

-- "We're checking" a Ferrari mechanic said to Charles Leclerc.    
 
Basically you stop and check why your code isn't working correctly. 

**2 types of errors**

1. ***Syntax Errors***: you didn't use the correct syntax.
2. ***Logic Errors***: the code doesn't do what you want. A logic error is like baking a cake and    using 1 spoon of sugar when the recipe said 3. It works, but the cake is bland.


## How Variables and Loops Work Together?

For example: 

Imagine you want to greet each of 3 guests:

	for (let i = 1; i <= 3; i++) {
		let guestName = "Guest " + i;
		console.log("Welcome, " + guestName + "!");
	}

This creates a new variable each time with a different name:

Welcome, Guest 1!  
Welcome, Guest 2!  
Welcome, Guest 3!

## How to Debug

1. Use your browser, Chrome works perfectly
2. Press [Cmd] + [Option] + [I] or right-click > Inspect 
3. Go to the **console** tab 

For a syntax error your Console will say something like: 

	! Uncaught ReferenceError: sayHy is not defined


## Breakpoints 

Open the **Sources** tab, click the line number you want to pause on. You'll see a blue dot appear, that is the breakpoint. 

Now when the code runs, it stops at that line, so you can:
	•	Check what variables contain
	•	Go step-by-step to see what happens next

You can control the code like a video:  
- ▶️ Resume (play)  
- ⏭ Step over (go to next line)
- ⬇️ Step into (go into a function)
- ⬆️ Step out (exit a function)

## Watch Variables

Once paused, hover over a variable like i or tabla and you’ll see its value in a small popup.

Or:

- Open the “Watch” panel
- Click the + to add a variable name
- It will keep showing you the current value as you go

## Console

Use console.log() to print messages while coding. This is your new best friend. 

Examples:

	console.log("Code reached here!");
	console.log("i =", i);
	console.error("Something went wrong!");
	console.dir(myObject);

--> These don't change the code, they tell you what's going on inside. It's a key *tool for debugging*

Think of the console as a chat window between the developer (you) and the code. 

In **Chrome**:
1. Right-click on any part of a web page and select **Inspect**.
2.	Go to the **Console** tab at the top of the Developer Tools window.
- Or press [[Cmd] + [Option] + [I]] (Mac) to open DevTools.
- Then press [[Esc]] if you only want the console to pop up at the bottom.


### What does console do?

1. Show errors (console tab in browser) 
2. Show messages you choose (console.log())
3. Test JavaScript directly. 



## Additional notes 

- JS doesn't change your HTML file - just what's display on the page. 


## Variables 
You can declare a variable with "var" or "let".
**let** when you’re working in modern JavaScript (it’s more flexible and safer than var).

- *const* – like *let*, but cannot be changed after it’s set.

Example:

	let name = "Lía";
	const country = "Mexico";  

	name = "Ana";      // ✅ allowed
	country = "Spain"; // ❌ error: can't change const

### Naming variables 

Valid options: 

	let myAge;
	let _box123;

Invalid options: 

	let 123abc;     // starts with number
	let my age;     // has a space
	let for = 5;    // uses a reserved word

> **Important**: JavaScript is case sensitive. 

	let Age = 25;
	let age = 30;
	// These are two different variables!

### Data Type 

1. Numbers (Ex. let x = 5;)
2. String (Ex. let name = "Lía";)
3. Boolean (true or false values)



String

	let name = "Lía";
Boolean

	let isHappy = true;


## Operators 

**Arithmetic Operators** (for numbers):

	let a = 10;
	let b = 5;

	console.log(a + b); // 15
	console.log(a - b); // 5
	console.log(a * b); // 50
	console.log(a / b); // 2

or 

	a++; // same as: a = a + 1;

Use the correct syntax as maths. 

**String Concatenation**: You can combine variables. 

	let firstName = "Lía";
	let lastName = "Nevárez";
	let fullName = firstName + " " + lastName;
	// fullName = "Lía Nevárez"

Be careful of mixing numbers and strings

	let a = 1;
	let b = "1";
	console.log(a + b);        // "11" (string!)
	console.log(a + Number(b)); // 2 (number)


**Comparison Operators**: 

These return *true* or *false*

	let age = 20;

	console.log(age == 20);  // true
	console.log(age > 21);   // false
	console.log(age <= 25);  // true

4. **Logical Operators**

| Operator | Meaning | Example                               |
|----------|---------|---------------------------------------|
| &&       | and     | age > 18 && age < 30                  |
| `        |         | `                                     |
| !        | not     | !isLoggedIn  (if false, becomes true) |


**Assignment Operators**

These change the value of a variable:

	let score = 10;
	score += 5;  // score = score + 5 → 15
	score -= 2;  // score = score - 2 → 13

## Dialog Boxes 

**alert()**

	alert("Welcome to my website!");

**confirm()** Asks the user yes/no

	let result = confirm("Do you want to delete this?");
	console.log(result);  // true or false

**prompt()** Ask the user for input:

	let name = prompt("What's your name?");
	alert("Hi " + name);

> ⚠️ prompt() always returns a string — convert it with Number() if needed.

For example:

	let age = prompt("How old are you?");
	age = Number(age);
	age = age + 1;
	document.write("Next year, you will be " + age + " years old");


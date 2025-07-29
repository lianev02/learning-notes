# Structure control 

By default, JavaScript runs code line by line, in order. But control structures you can change that flow, for example:
- Run code only if something is true
- Run different code depending on a condition
- Repeat code several times (that will be loops, later)

## Conditionals 

Conditionals help the computer make decisions.

### Summary

| Structure              | Syntax Example                                                                 | Description                                                                                     |
|------------------------|--------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|
| `if`                   | `if (condition) { code }`                                                      | Executes the code block if the condition is `true`.                                            |
| `if...else`            | `if (condition) { code } else { otherCode }`                                   | Executes one of two blocks based on the condition.                                              |
| `if...else if...else`  | `if (cond1) { code1 } else if (cond2) { code2 } else { code3 }`                | Checks multiple conditions sequentially.                                                        |
| Ternary Operator       | `condition ? valueIfTrue : valueIfFalse`                                       | Shorter syntax for a simple `if...else` assignment.                                             |
| `switch`               | `switch(variable) { case value: code; break; ... default: code; }`             | Selects a code block to execute based on matching a value.                                     |

### If / Else Statements (Conditional with 1 or 2 branches)

Run code only if certain that condition is met. 

    if (condition) {
    // Code runs only if the condition is true
    } else {
    // Code runs if the condition is false
    }

### Ternary Operator (Short If/Else)

Shorter version to write condition
    
    (condition) ? valueIfTrue : valueIfFalse

For example: 

    var age = parseInt(prompt("Your age:"));
    var message = (age > 18) ? "Adult" : "Minor";
    document.write(message);

### Switch Statement (Multi-Branch Conditional)

To compare one variable against many possible values. 

    switch (variable) {
    case value1:
        // do something
        break;
    case value2:
        // do something else
        break;
    default:
        // fallback if no case matches
    }

For example: 

var day = parseInt(prompt("Enter day number:"));

    switch (day) {
    case 1: document.write("Monday"); break;
    case 2: document.write("Tuesday"); break;
    case 3: document.write("Wednesday"); break;
    case 4: document.write("Thursday"); break;
    case 5: document.write("Friday"); break;
    case 6: document.write("Saturday"); break;
    case 7: document.write("Sunday"); break;
    default: document.write("Invalid value");
    }

> *break* stops the execution from continuing into the next case. 

### Nested Conditionals

Chain multiple conditions

    if (condition1) {
    // if condition1 is true
    } else if (condition2) {
    // if condition2 is true
    } else {
    // if none of the above are true
    }

For example: Water temperature 

    var temp = parseFloat(prompt("Water temperature:"));

    if (temp <= 0) {
    document.write("ICE");
    } else if (temp > 0 && temp < 100) {
    document.write("LIQUID");
    } else {
    document.write("VAPOR");
    }




## Repetitive

- Repetitive structures or **loops** let you repeat a block of code multiple times, either a fixed number of times or until a condition is met. Like checking items off a to-do list: Step 1, Step 2, Step 3… until all done.  

Another example could be when Spotify loads your playlist, it loops through all your songs and displays them one by one.

### Summary 

| Loop Type         | Description                                                                 | When Condition Is Checked | Guaranteed to Run at Least Once? | Examples                                      |
|-------------------|-----------------------------------------------------------------------------|----------------------------|-----------------------------------|--------------------------------------------------------|
| `for`             | Repeats code a set number of times with a counter                          | Before each loop           | No                                | Counting from 1 to 10                                 |
| `while`           | Repeats code while a condition is true                                      | Before each loop           | No                                | Ask password until it's correct                       |
| `do...while`      | Like `while`, but always runs once before checking the condition            | After each loop            | Yes                               | Ask password at least once, even if it’s correct       |
| `break`           | Immediately exits the loop                                                  | —                          | —                                 | Stop showing numbers once you hit 5                   |
| `continue`        | Skips to the next loop iteration, ignoring the rest of current iteration    | —                          | —                                 | Skip number 5 in a list from 0 to 9                   |

### Repeat x times (`for`)

A  `for` loop is used when you know exactly how many times you want something to repeat. 

Structure:

    for (start; condition; update) {
    // code to repeat
    }

Example: 

    for (let i = 1; i <= 5; i++) {
    console.log(i);
    }

- Start at `i = 1`
- Keep going while `i` is less than or equal to 5 
- After each loopp, add 1 to `i`

### Reapeat `while`something is true 

Keeps repeating as long as the condition is true. 

    while (condition) {
    // code to repeat
    }

> **Important**: If the condition is false at the start, it won’t run even once.


### `do ... while` loop 

"Do first, then check"
A `do...while` loop is like a while, but it *runs at least once*, even if the condition is false.

Structure: 

    do {
    // code to run at least once
    } while (condition)


### `break` loop 

"Stop the loop early"
`break` makes the loop stop immediately, no matter the condition.

Example:

    for (let x = 0; x < 10; x++) {
    if (x === 5) break;
    console.log(x);
    }

In the example, the output wil be 0, 1, 2, 3, 4, and the loop stops when x is 5. 

### `continue` loop 

"Skip one loop step"
`continue` skips the rest of the current loop and goes straight to the next turn.

    for (let x = 0; x < 10; x++) {
    if (x === 5) continue;
    console.log(x);
    }

Output: 0, 1, 2, 3, 4, 6, 7, 8, 9 (5 is skipped)

Imagine you’re eating 10 cookies but you throw away cookie #5 because it fell on the floor. You skip it and continue eating the others.
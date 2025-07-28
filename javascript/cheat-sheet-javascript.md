# JavaScript Cheat Sheet 

- `prompt("message")` → Always returns a string or null.
- `Number(value)` → Converts a string to a number. NaN if not valid.
- `isNaN(value)` → Returns true if value is Not a Number. 

    let value = prompt("Enter a number:");
    let num = Number(value);

    if (isNaN(num)) {
    alert("That's not a number!");
    }

> It's better if you use both `Number()` and `isNaN()`

- Variables:
    - var: function scoped (can be hoisted and are initialized as `undefined`).
    - let / const: block scoped (safer).
- `document.write()` → Immediately writes to the page. It replaces everything if called after the page is loaded.
- `return` ends a function and sends a value back. Gives a result back. 

## `parseFloat()`

`parseFloat()`is a built-in JavaScript function that:
- Converts a string into a floating-point number (i.e. decimals are allowed).
- It stops parsing when it reaches a non-number character.

Example:

    parseFloat("3.14")   // → 3.14
    parseFloat("5px")    // → 5
    parseFloat("abc")    // → NaN

> When to use it: when you expect the input might contain a decimal number and it came as a string (which is always the case from an `<input>`).

How is it different from Number()?
- Number() is stricter. It tries to convert the whole string, and returns NaN if it doesn’t make sense as a full number.

Example: 

    Number("3.14")    // → 3.14
    Number("5px")     // → NaN  ❌
    Number("abc")     // → NaN

> Use `Number()` when you only want to accept clean, numeric input like "42" or "3.5" — no units, no mixed strings.

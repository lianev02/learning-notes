# DOM (Document Object Model)

Is one of the most important concepts to understand. 
Think of DOM like a family tree of the website. 

Every HTML tag (like `<h1>`, `<a>`, `<p>`, `<img>`) becomes an object inside this tree.
These objects are nested hierarchically: the `<html>` tag is the root, then `<head>` and `<body>`, and inside `<body>` you have children like `<h1>` or `<a>`.

## Why is the DOM important?

Because JavaScript and jQuery use the DOM to interact with the page. Without the DOM, you couldn’t:
- Change text or images dynamically.
- Hide or show elements.
- Capture what a user typed in an input.
- Change the color or style of something when the user clicks.
 
## Key takeaways

The HTML file is static (stored on the server).
But once loaded in the browser, **JavaScript/jQuery can modify the DOM**, which means it changes what the user sees.

These changes do not affect the original file on the server.

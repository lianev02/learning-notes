# Selectors

This is one of the most powerful parts of the library, because if you can select the right element(s) from the DOM, you can do anything with them (change text, add CSS, hide them, animate them, etc.).

## What are jQuery selectors? 

A selector tells jQuery which element(s) you want to work with in the DOM.

Think of it as pointing your finger: “I want to change THIS element (or all of these ones).”

They are written inside **`$()`** which is just shorthand for `jQuery()`.

    $("#title")  // selects the element with id="title"
    $(".highlight") // selects all elements with class="highlight"
    $("p") // selects ALL <p> tags

## Making sure the page is loaded

Before selecting elements, you need to make sure the page is ready.
That’s why we wrap everything in:

    $(document).ready(function () {
    // your code here
    });

Or the shorter version 

    $(function () {
    // your code here
    });

> This is the document ready function in jQuery. It means: “Wait until the page (DOM) is fully loaded, then run my code.”

Inside that block you’ll write your selectors and then call methods to change them. For example:

    $(function () {
        $("p").hide();          // hide all <p> elements
        $("#demo").text("Hi!"); // change text of #demo
        $(".box").css("color", "blue"); // change all .box text to blue
    });


## Types of selectors


| Selector            | Description                                                                 | Example                  |
|---------------------|-----------------------------------------------------------------------------|--------------------------|
| `*`                 | Selects **all elements**                                                   | `$(" * ")`              |
| `#id`               | Selects the element with a specific **id**                                 | `$("#myId")`            |
| `.class`            | Selects all elements with a specific **class**                             | `$(".myClass")`         |
| `element`           | Selects all elements of a specific type/tag                                | `$("p")`                |
| `element1,element2` | Selects **multiple elements** separated by a comma                         | `$("h1, p, div")`       |
| `parent > child`    | Selects all **direct children** of the parent                              | `$("ul > li")`          |
| `ancestor descendant` | Selects all **descendant elements** (not only direct children)           | `$("div p")`            |
| `:first`            | Selects the **first** element of the selection                             | `$("p:first")`          |
| `:last`             | Selects the **last** element of the selection                              | `$("p:last")`           |
| `:eq(n)`            | Selects the element with a specific **index (0-based)**                    | `$("li:eq(2)")`         |
| `:even` / `:odd`    | Selects elements with **even/odd index**                                   | `$("tr:even")`          |
| `[attribute]`       | Selects elements with a given **attribute**                                | `$("[href]")`           |
| `[attr='value']`    | Selects elements with an **attribute = value**                             | `$("[type='text']")`    |
| `:contains(text)`   | Selects elements containing the specified **text**                         | `$("p:contains('Hello')")` |
| `:hidden` / `:visible` | Selects elements that are **hidden/visible**                           | `$("div:hidden")`       |

## jQuery Pseudo-Selectors

### Input Selectors
| Selector      | Description |
|---------------|-------------|
| `:input`      | Selects all `<input>`, `<textarea>`, `<select>`, and `<button>` elements |
| `:text`       | Selects all text input fields (`<input type="text">`) |
| `:password`   | Selects all password fields (`<input type="password">`) |
| `:radio`      | Selects all radio buttons (`<input type="radio">`) |
| `:checkbox`   | Selects all checkboxes (`<input type="checkbox">`) |
| `:submit`     | Selects all submit buttons (`<input type="submit">`) |
| `:reset`      | Selects all reset buttons (`<input type="reset">`) |
| `:button`     | Selects all buttons (`<button>` and `<input type="button">`) |
| `:file`       | Selects all file upload fields (`<input type="file">`) |
| `:image`      | Selects all image input fields (`<input type="image">`) |

---

### State Selectors
| Selector         | Description |
|------------------|-------------|
| `:enabled`       | Selects all enabled form elements |
| `:disabled`      | Selects all disabled form elements |
| `:checked`       | Selects all checked checkboxes or radio buttons |
| `:selected`      | Selects all selected options in a dropdown |

---

### Visibility Selectors
| Selector     | Description |
|--------------|-------------|
| `:visible`   | Selects all visible elements |
| `:hidden`    | Selects all hidden elements |

---

### Position Selectors
| Selector         | Description |
|------------------|-------------|
| `:first`         | Selects the first element |
| `:last`          | Selects the last element |
| `:even`          | Selects all even-indexed elements (0-based) |
| `:odd`           | Selects all odd-indexed elements (0-based) |
| `:eq(n)`         | Selects the element with index *n* |
| `:gt(n)`         | Selects all elements with index greater than *n* |
| `:lt(n)`         | Selects all elements with index less than *n* |
| `:header`        | Selects all header elements (`<h1>` to `<h6>`) |
| `:animated`      | Selects all elements currently being animated |

---

### Content Selectors
| Selector         | Description |
|------------------|-------------|
| `:contains("text")` | Selects all elements containing the specified text |
| `:empty`         | Selects all elements with no children (including text nodes) |
| `:has(selector)` | Selects elements that contain at least one element matching the selector |
| `:parent`        | Selects all elements that are parents (have child elements) |


Do reference the official jQuery website. 


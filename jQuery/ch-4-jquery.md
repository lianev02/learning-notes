# jQuery Filters

Filters refine a selection. You start by selecting elements, then apply a filter to narrow them down.

## Summary 

> Use `.filter()` when you want to keep certain elements.
> Use `.not()` when you want to exclude.
> Prefer methods (`.eq(), .first(), .last()`) over pseudo-selectors — they are faster.

## 1. `.filter()`
Keeps only the elements that match a condition.

By selector

    $("ul li").filter(".current"); 
    // keeps only <li> with class="current"

By function

    $("ul li").filter(function(index, element) {
    return $(element).text().indexOf("_") > -1;
    });
    // keeps only <li> that contain "_"

## 2. `.not()`

Excludes elements from the selection.

    $("ul li").not(":contains('_')"); 
    // selects <li> that do NOT have "_"

## 3. Other filter methods

These are faster alternatives to pseudo-selectors.

| **Selector Version** | **Filter Method Equivalent** |
|-----------------------|------------------------------|
| `:eq(n)`             | `.eq(n)`                     |
| `:first`             | `.first()`                   |
| `:last`              | `.last()`                    |
| `:has(selector)`     | `.has(selector)`             |




Example:

    $("#capa1 p:eq(2)").css("color","red");   // selector version

    $("#capa2 p").eq(2).css("color","red");   // filter method version



## Chaining filters

Every filter (like .find(), .eq(), .not(), etc.) returns a new jQuery object (a new selection).
That means you can chain them one after another to refine or apply multiple operations without writing new $() selections every time.


Example 1: Find + eq + html

    $("#content")
        .find("h3")   // busca todos los <h3> dentro de #content
        .eq(2)        // se queda solo con el tercer <h3> (índice 2)
        .html("nuevo contenido");  // cambia su contenido

Only the third `<h3>` inside #content is modified.


Example 2: Using .end()

Sometimes you need to “go back” to the previous selection to keep working with it. That’s what .end() does.

    $("div")
    .eq(0).css("background-color","red").end()   // capa 1 → rojo, luego volvemos a $("div")
    .eq(1).css("background-color","green").end() // capa 2 → verde, luego volvemos a $("div")
    .eq(2).css("background-color","blue");       // capa 3 → azul

- Without .end(), after .eq(0) you’d lose access to the original list of `<div>`.
- .end() restores the previous selection so you can apply another filter.

## `.is()` filter

`.is(selector)` → returns true or false depending on whether at least one element in the current selection matches the selector.

It’s mostly used in conditions (if statements).

Example

    if ($(':radio').is(':checked') == false) {
        alert("No se marco");  
    } else {
        alert("Se marco: " + $(':radio:checked').val());
    }

    $(' :radio ') → selects all radio buttons.
    .is(':checked') → true if any radio button is checked.

If none is checked → alert "No se marco".
Else → find which one is checked and show its value.


### Summary
Chaining = keep applying filters without rewriting $().
.end() = “go back” to the previous selection in the chain.
.is() = test condition → returns true/false if selection matches something.

**Tip:**
Think of jQuery chaining like working with layers of a Photoshop project:
You zoom in (with .find(), .eq(), etc.).
If you go too deep, .end() lets you zoom back out to the bigger selection.
And .is() is like asking: “Does this layer have a certain property?”




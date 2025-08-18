# Javascript Review 


- **Array** → Stores multiple values in an ***ordered list*** (indexed with numbers starting from 0).
    - Ordered by index 
- **Object** → Stores data in ***key–value pairs*** (keys are usually strings, not numbers).
    - Accessed by key name
- To find out how many items are stored inside an array in JS you use `array.length`. 

For example: 

    let fruits = ["apple", "banana", "cherry"];
    console.log(fruits.length); // 3

## Loops 
- `for` → good for looping through array indexes in order (0 to length - 1), like listening to a playlist in its set order.
- `for...in` → loops through keys (good for objects or associative arrays, not ideal for normal arrays).
- `for...of` → loops directly through values in arrays.


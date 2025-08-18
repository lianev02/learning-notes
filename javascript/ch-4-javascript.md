# Arrays 

An array is like a bookshelf with numbered compartments. Each compartment (index) holds one book (value), and you can quickly access any book by knowing its number (position).

> It’s one variable that stores multiple values in order.

You keep several things in a single bag. You can reach in and pull out item 0 (“milk”), item 1 (“eggs”), etc.

    let groceries = ["milk", "eggs", "bread"];

> **Definition**: a data structure used to store multiple values in a single variable
## Declaring Arrays 

    var fruits = ["apple", "banana", "orange"];

Think of fruits as a shelf with:
- fruits[0] = “apple”
- fruits[1] = “banana”
- fruits[2] = “orange”

You can also start empty and fill it later:

    var fruits = [];
    fruits[0] = "apple";
    fruits[1] = "banana";

## Accessing Elements 

Each item in the array has an index (starting from 0):

    console.log(fruits[1]); // "banana"

This is like saying: “Give me the book on shelf 1”.

## Length of an array

    console.log(fruits.length); // 3

This tells you how many compartments (values) are in your bookshelf (array).

## Looping through arrays

You can loop through arrays in three ways. Let’s use:

    var days = ["Monday", "Tuesday", "Wednesday"];

### `for` loop 

    for (let i = 0; i < days.length; i++) {
    console.log("Day at position", i, "is", days[i]);
    }

Use it when: You need both the index and the value.


### `for ... in` loop
    
    for (let index in days) {
    console.log("Index:", index, "Value:", days[index]);
    }

Use it when: You mostly care about the index.

### `for ... of` loop

    for (let day of days) {
    console.log("Day:", day);
    }

Use it when: You just care about the value, not the index

### Example 

Imagine you’re building Spotify. A user’s playlist is an array:

    let playlist = ["State of Grace", "Red", "Treacherous"];

Instead of creating a separate variable for each song, we group them in one *array*. Each song is stored in a numbered position (called an index), starting from 0.



**`for` loop** → A curated playlist played in order
- You play each song in order, using its track number (index).

Example: 

    for (let i = 0; i < playlist.length; i++) {
    console.log(`Now playing track ${i}: ${playlist[i]}`);
    }

**`for...in` loop** → Reading the back of a record
- You read each track number first (index), then look up the corresponding song.

    for (let trackNumber in playlist) {
    console.log(`Track ${trackNumber}: ${playlist[trackNumber]}`);
    }

You’re holding the vinyl sleeve and reading:
Track 0 – State of Grace
Track 1 – Red
Track 2 – Treacherous

You’re more focused on positions (indexes) than the songs themselves.

**`for...of` loop** → Vibing with the Playlist 
You play every song in the playlist, one after another, without caring about their track number.

    for (let song of playlist) {
    console.log(`Now playing: ${song}`);
    }

Just press Play. You’re enjoying each song in order without needing to know what number it is.

## Associative Arrays (Objects)

An **associative array** (or object) is like a cabinet where you label each drawer with a word, not a number. You store a value inside each drawer, and access it by calling the label.

You don’t look up a value by number (like in normal arrays), but by a **key** (which can be a string or any unique identifier).

Think of a user profile on an app:
    
    let user = {
    name: "Laura",
    age: 22,
    city: "Barcelona"
    };

Instead of saying “give me the value at position 1”, you say:
- user["name"] ➝ "Laura"
- user["city"] ➝ "Barcelona"
Or even:
- user.name ➝ "Laura"

Associative arrays are best when you want to store values with labels, not positions.
>Objects (associative arrays) are better when you need meaning behind the data.

### Example 

    let cartItem = {
    product: "Laptop",
    price: 899.99,
    quantity: 2,
    inStock: true
    };

    let totalPrice = cartItem.price * cartItem.quantity;

## Declaring arrays

1. Declare an object with key-value pairs. Use the curly brackets **{ }**. 
    
        let user = {
        name: "Nerea",
        age: 22,
        language: "Catalán"
        };

2. Accessing a value 

        user.name        // "Lía"  ✅ dot notation - key is a simple 1 word name
        user["country code"]     // "593" ✅ bracket notation - key has space or special characters. Or accessing the key dynamically. 

## Checking if a key already exists

To check if a key is already inside an object before using or changing its value.

    let shoppingList = {
    milk: 2,
    eggs: 12,
    bread: 1
    };

Now you want to check if “milk” is already on your list:

    if ("milk" in shoppingList) {
    console.log("Milk is already on the list");
    }

`in` checks if that key exists in the shoppingList object.

- You want to avoid adding duplicates 
- You want to know what's missing 

**Other Example** 

    let inventory = {
    sword: 1,
    potion: 3
    };

    if ("potion" in inventory) {
    console.log("You already have potions 🧪");
    } else {
    console.log("Go find some potions!");
    }

## Looping Through Associative Arrays (Objects)

Goal: To go through each key and value inside an object, one by one.

**Example** 

Let’s say you’re checking what’s in each room in your house:

    // Step 1: Create an associative array (object)

    let house = {
    kitchen: "fridge",
    bathroom: "towel",
    bedroom: "pillow"
    };

    // Step 2: Loop through each key (room name) in the object

    for (let roomName in house) {
   
    // Step 3: Get the value (item in that room)

    let item = house[roomName];

    // Step 4: Output a sentence

    console.log("In the " + roomName + " there is a " + item);
    }

Output: 

    In the kitchen there is a fridge
    In the bathroom there is a towel
    In the bedroom there is a pillow

> Tip: Use template literals (more modern & cleaner): 
    
    for (let roomName in house) {
    let item = house[roomName];
    console.log(`In the ${roomName} there is a ${item}`);
    }


## Array Handling Functions (Methods)

Arrays come with **predefined methods** that make it easy to manipulate them. The basic syntax is `array.method(arguments)`

So yes, handling functions let you manipulate or “handle” what you see, extract, or modify, and whether the main array changes depends on the method.


| Method       | Description                                                   | Analogy / How to Think About It                       | Example                                                                 |
|--------------|---------------------------------------------------------------|------------------------------------------------------|-------------------------------------------------------------------------|
| `concat()`   | Combines two arrays into a new array                          | Merging two playlists                                | `[1,2].concat([3,4]) // [1,2,3,4]`                                      |
| `indexOf()`  | Returns the position of a value; -1 if not found              | Searching for a song in a playlist                   | `["apple","banana"].indexOf("banana") // 1`                              |
| `lastIndexOf()` | Returns the last occurrence of a value                       | Finding the last time a song appears in a playlist  | `["a","b","a"].lastIndexOf("a") // 2`                                    |
| `join()`     | Converts array into a string separated by a character         | Printing playlist as a list of song names           | `[1,2,3].join("-") // "1-2-3"`                                           |
| `toString()` | Converts array into a string with commas                      | Same as join() with commas                           | `[1,2,3].toString() // "1,2,3"`                                         |
| `reverse()`  | Reverses the order of the array                                | Playing playlist backwards                           | `[0,1,2,3].reverse() // [3,2,1,0]`                                      |
| `push()`     | Adds a value to the end of the array                           | Stack: adding plates on top                          | `let arr=[]; arr.push("a") // ["a"]`                                     |
| `pop()`      | Removes a value from the end of the array                      | Stack: removing top plate                             | `arr.pop() // "a"`                                                      |
| `unshift()`  | Adds a value to the beginning of the array                     | Queue: new person joins front                        | `let q=[]; q.unshift("a") // ["a"]`                                     |
| `shift()`    | Removes a value from the beginning of the array                | Queue: first person gets served                      | `q.shift() // "a"`                                                      |
| `slice()`    | Returns a subarray from start index to end index (exclusive)   | Selecting a section of a playlist                     | `[0,1,2,3,4,5].slice(2,5) // [2,3,4]`                                   |
| `sort()`     | Sorts array values                                              | Alphabetizing songs or sorting numbers              | `["c","a","b"].sort() // ["a","b","c"]`                                 |
| `splice()`   | Add/remove elements at a specific index                        | Insert/remove songs at a specific spot in playlist   | `[1,2,3,4].splice(1,2,"a","b") // [1,"a","b",4]`                        |

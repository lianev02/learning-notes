# Objects 

Think of an object like a toolbox. 
- Inside the toolbox you have tools (methods) → functions that do something.
- You also have labels/info (properties) → data stored about that object.

Example: A Bank Account object
	•	Properties: account number, owner, balance.
	•	Methods: deposit(), withdraw(), calculateInterest().

> So an object = data + actions (behaviours) combined in one package. 

## 2 ways to create objects 

1. **JSON style** 
    - Quick and one-off
    - Think of it as filling out the form for a single customer.
    - Use it for 1 or 2, for more, use constructors.

Example:

    let account = {
    owner: "Alice",
    balance: 1000,
    interest: 0.02,
    deposit: function(amount) {
        this.balance += amount;
    },
    withdraw: function(amount) {
        this.balance -= amount;
    }
    };

2. **Constructor Functions**
    - It's like making a mold, then you can do as many as you want. More like a template. 

Example:

    function BankAccount(owner, balance, interest) {
    this.owner = owner;
    this.balance = balance;
    this.interest = interest;

    this.deposit = function(amount) {
        this.balance += amount;
    };

    this.withdraw = function(amount) {
        this.balance -= amount;
    };

    this.calculateInterest = function() {
        return this.balance * this.interest;
    };
    }

Then you can create many accounts with the same "recipe":

    let account1 = new BankAccount("Alice", 1000, 0.02);
    let account2 = new BankAccount("Bob", 500, 0.03);

    account1.deposit(200);
    account2.withdraw(100);

Each account is independent but follows the same blueprint. 

## `this` keyword

- `this` = "me, the current object"

**Analogy** 
If you and your friend both have backpacks:
- In your backpack, this.waterBottle refers to your bottle.
- In your friend’s backpack, this.waterBottle refers to their bottle. 

So this changes depending on which object is calling the method.

    let box1 = {
    a: 2,
    b: 3,
    multiply: function() {
        return this.a * this.b; // refers to box1's a and b
    }
    };

    let box2 = {
    a: 5,
    b: 10,
    multiply: function() {
        return this.a * this.b; // refers to box2's a and b
    }
    };

    console.log(box1.multiply()); // 6
    console.log(box2.multiply()); // 50

## Accessing and Using Objects
Get a property: 

    console.log(account.balance);

Change a property:

    account.interest = 0.05;

Call a method:

    account.deposit(100);

## Example 
To make a square object:

    function Square(base, height) {
    this.base = base;
    this.height = height;
    this.area = function() {
        return this.base * this.height;
    };
    }

Now you can create multiple squares: 

    let sq1 = new Square(4, 5);
    let sq2 = new Square(6, 6);
    let sq3 = new Square(10, 2);

    console.log(sq1.area()); // 20
    console.log(sq2.area()); // 36
    console.log(sq3.area()); // 20

# Accessing JavaScript Properties

JavaScript properties are the values associated with a JavaScript object, which is a collection of unordered properties. We give an object properties that are unique to it so we are able to store them and, later on, retrieve them. In the grand scheme of things, this helps us keep our objects clean and consistent for when we want to retrieve certain values down the road. Now for the purposes of this blog, let's assume we have a monthly box subscription that offers a videogame of the month with a few trinkets that follow a certain theme. We have been very successful and now we have a massive database full of different customers (each individual customer would be an object in this case), and each customer has values associated with them, such as their first name, last name, address, phone number, email, previous orders, etc:

```javascript
  const customer1 = {
    firstName: "Rick",
    lastName: "Sanchez",
    address: "C 137, Citadel of Ricks",
    phone: "555-123-rick",
    email: "morty_suckz@rickmail.com"
  }
```

Now Rick is one of our loyal customers and has been for quite sometime, so we want to send him a small thank you gift. Along with that gift we also want to add a handwritten letter for that extra touch. Since he's our first customer we know he has an ID of 1 and it's easy to locate him, but now we want to access his info. We can think of an object as an associative array. The keys in this array are the names of the object's properties. We have two ways to access an object in JavaScript:

1. Dot Notation
2. Bracket Notation

### Dot Notation

The variables and methods of an object are called the members of that object and the members of an object are accessed using dot notation, which is used most frequently. We access those properties on an object by specifying the name of the object, directly followed by the name of the property we are looking for that belongs to that object(`object.property`). For example if we want to find the first name of our customer, we can do something like this:

```javascript
  customer1.firstName 
  // => "Rick"
  
  customer1.lastName 
  // => "Sanchez"
```

Since we developers are lazy, we can have JavaScript do the work of adding both names and returning our loyal customer's full name:

```javascript
  fullName = customer1.firstName + " " + customer1.lastName
  
  Console.log(fullName)
  // => Rick Sanchez
```
Dot notation is much easier to read than bracket notation and is used more often due to that fact.

### Bracket Notation

With bracket notation, we use the computed member access operator, which is a pair of square brackets []. We can get the same effect from using the dot notation using bracket notation as well:

```javascript
  customer1['firstName']
  // => "Rick"
  
  customer1['lastName']
  // => "Sanchez"
```

Bracket notation is a bit harder to read than dot notation. However, there are two main situations where we use bracket notation. 
  1. **Whenever we have non-standard keys**. Meaning that the string we used as our key is non-standard, which ranges from having periods in the key, hyphens, symbols, and spaces (Typically we want to camelCaseEverything). For instance:
  
  ```javascript
    customer1.'plumbuses returned: customer_wasnt_a_fan';
    // ERROR: Uncaught SyntaxError: Unexpected string
    
    customer1['plumbuses returned: customer_wasn't_a_fan'];
    // => "None, everyone has a plumbus in their home"
  ```
  2. **Whenever we want to dynamically access properties**. With brackets, we can place any expression inside the brackets and the JavaScript engine will compute its value to figure out which property to access:
  
  ```javascript
    customer1['first' + 'Name']
    // => "Rick"
  ```
  
  The main benefit of accessing properties dynamically is the ability to compute the value of variables or constants that we can assign. Circling back to our initial object, let's say we want to assign address as the multiverse:
  
  ```javascript
   const customer1 = {
    firstName: "Rick",
    lastName: "Sanchez",
    address: "C 137, Citadel of Ricks",
    phone: "555-123-rick",
    email: "morty_suckz@rickmail.com"
   }
  
   let multiverse = 'address';
  
   customer1[multiverse]
   // => "C 137, Citadel of Ricks"
   customer1['address']
   // => "C 137, Citadel of Ricks"
  
   customer1.multiverse
   // => undefined
  ```
So bracket notation is not as explicit as the dot notation and allows us to pass it keys that either are not in conventional camelCase or include numbers. JS evaluates the first complete expression with square brackets in a statement, runs toString() on it to convert it into a string and then uses that value for the next bracket expression, and just keeps going until there's no more expressions to run.

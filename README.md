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

The variables and methods of an object are called the members of that object and the members of an object are accessed using dot notation. For example if we want to find the first name of our customer, we can do something like this:

```javascript
  customer1.firstName = "Rick"
```

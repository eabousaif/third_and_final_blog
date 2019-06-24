# Accessing JavaScript Properties

JavaScript properties are the values associated with a JavaScript object, which is a collection of unordered properties. We give an object properties that are unique to it so we are able to store them and, later on, retrieve them. Let's assume we have a monthly box subscription that offers a videogame of the month with a few trinkets that follow a certain theme. We have been very successful and now we have a massive database full of different customers (each individual customer would be an object in this case), and each customer has values associated with them, such as their first name, last name, address, phone number, email, previous orders, etc:

```javascript
  const customer1 = {
    firstName: "Rick",
    lastName: "Sanchez",
    address: "The entire multiverse",
    phone: "555-123-rick",
    email: "morty_suckz@rickmail.com"
  }
```


# XHR

## Introduction
XHR or XMLHttpRequests are a way to transfer data between the client and server without refreshing the page.

## Synchronous vs Asynchronous Requests
Up until this point in class everything we have done in JS has been a synchronous request.  This means that everything in our JS files has run one at a time and waited for the previous thing to finish before starting.  Until now that has been perfectly fine - we have defined all our arrays in main.js or we have used click events to add new data to those arrays.  But now we have a different situation - now we have data in a json file that we want to be able to pull into our code and then print it to the DOM.  Pulling data in from an outside source (no matter if it is a json file or API) take time.  It could take anywhere from a few milliseconds to a few minutes.  We have no way of knowing how long the data will take to come back - because of this we are now making an asynchronous request.

A better way of thinking about synchronous requests is to think about buying a ticket at a movie theater.  Everyone gets into line and the first person buys their ticket.  When that person is done the next person buys their ticket.  Then the next and so on.

A better way of thinking about an asynchronous request is to think about a restaurant.  Every group sits at separate tables. At any time a waiter comes over and takes the tables order.  Then the kitchen receives the orders and cooks the food.  The waiter then brings the food out to the correct table.  One table doesn't have to wait for the previous table to order, have their food cooked, and get delivered before they can place their orders - each table happens independently.

In JavaScript asynchronous calls generally have callback functions.  These functions are instructions for JS on what should happen when the data comes back.

## Constructors
In JavaScript constructors are a special type of object with predetermine properties used when you want to make multiple copies of the same basic structure.  You can think of them as blueprints.  You can build your own constructor or use some of the built in constructors.

Here is an example of a simple constructor that I hve built:
```js
function Book(name, year) {
  this.name = name;
  this.year = `(${year})`;
}
```
This constructor could be used to build up a library of books.  Each time I am ready to add a new book to my collection I can instantiate the Book constructor and pass in the new name of the book and the year it was written.  To do this I need to use the `new` keyword:

```js
const firstBook = new Book("Pro AngularJS", 2014);
const secondBook = new Book("Secrets Of The JavaScript Ninja", 2013);
const thirdBook = new Book("JavaScript Patterns", 2010);
```

I now have three books that were all created from the same Book constructor so each one has the same properties.

There are also some great built in constructors that you can use such as:

```js
const currentDateTime = new Date(); //this gets the current date/time stamp

const pets = new Array();  // this makes an array called pets
```

Another common JS constructor function is one that we will use to build up our XHR calls.

## Setting up an XHR Call
To write a vanilla JS XHR call we will use the XMLHttpRequest constructor.  The code for a simple request looks something like this:


```html
/* index.html */
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Theme Park</title>
  </head>
  <body>
    <div id="ride-container"></div>
    <script src="main.js"></script>
  </body>
</html>
```

```js
// main.js

const printToDom = (divId, textToPrint) => {
  const selectedDiv = document.getElementById(divId);
  selectedDiv.innerHTML = textToPrint;
};

const domStringBuilder = (arrayToPrint) => {
  let domString = '';
  arrayToPrint.forEach((ride) => {
    domString += `<h3>${ride.name}</h3>`;
  })
  printToDom('ride-container', domString);
};

function executeThisCodeAfterFileLoads(){
  const data = JSON.parse(this.responseText);
  domStringBuilder(data.rides);
}

function executeThisCodeIfXHRFails(){
  console.error('oh shit!');
}

const getRidesData = () => {
  const myRequest = new XMLHttpRequest();
  myRequest.addEventListener('load', executeThisCodeAfterFileLoads);
  myRequest.addEventListener('error', executeThisCodeIfXHRFails);
  myRequest.open('GET', './db/rides.json');
  myRequest.send();
};

const init = () => {
  getRidesData();
};

init();
```

Lets go through this code one line at a time.

To start we are running an `init` function when the page loads.  This function calls the   getRidesData  function.  This is the function that makes and executes our XHR call.  Let's look at the rest of the code:

```const myRequest = new XMLHttpRequest();```

The above line of code initializes the `XMLHttpRequest` constructor and assigns it to a variable called `myRequest`.  This means `myRequest` now has all the base properties and functions that were defined when that constructor was written.  We can now modify those properties with the properties that are relevant to the request we are making.

```js
myRequest.addEventListener('load', executeThisCodeAfterFileLoads);
```
This line of code adds an event listener to `myRequest`  the event type is a 'load'.  In this case that means a successful return of the request.  When a load event happens the XHR call will execute the function `executeThisCodeAfterFileLoads`.

```js
myRequest.addEventListener('error', executeThisCodeIfXHRFails);;
```
This line of code adds an event listener to `myRequest`  the event type is a 'error'.  This event will fire if there is a server error with the request. When a error event happens the XHR call will execute the function `executeThisCodeIfXHRFails`.

```js
myRequest.open('GET', './db/rides.json');
```
This line of code tells the request what type of request it is and from where.   In this case we are making a GET request and we are requesting the data from a file called rides.json located in the db folder.

```js
myRequest.send();
```

Now lets look at the two functions that run in response to the XHR call.  These function MUST be written with `function`.  DO NOT write them with an arrow function.  Using an arrow function changes the scope of the function and makes it so we can't use the `this` keyword.

The `executeThisCodeIfXHRFails` is the function that will run if the server comes back with an error.  Generally this function is used to log that an error happened.  We will do this with a `console.error` message.
```js
function executeThisCodeIfXHRFails(){
  console.error('oh shit!');
}
```

The `executeThisCodeAfterFileLoads` is the most important function in an XHR call.  It is the ONLY place we have access to the data from the XHR call.  The purpose of this function is to get the data, process it as needed, and send it off to be used.  When the data from the JSON file comes back it is a giant string.  We access it by typing `this.responseText`.  Here `this` is a javascript keyword that refers to the the call site.  Our call site is the XHR call itself because that call is what called the `executeThisCodeAfterFileLoads`.  So you can think of it as `this` = `myRequest`.  We take that giant string and use `JSON.parse` to turn it into a regular json object.
```js
function executeThisCodeAfterFileLoads(){
  const data = JSON.parse(this.responseText);
  domStringBuilder(data.rides);
}
```

Once we have the actual data array we can send it off to the `domStringBuilder` just like normal. The `domStringBuilder` can then build up the string to print to the dom and call the `printToDom` function.
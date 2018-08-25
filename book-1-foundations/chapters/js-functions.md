# Functions in JavaScript

Functions are reusable code. JavaScript written without functions executes one line of code at a time until complete.

```js
// Display the first and last name of the following people
let firstName = "Jamal";
let lastName = "Haynes";

console.log(`${firstName} ${lastName}`);

let firstName = "Debra";
let lastName = "Gordon";

console.log(`${firstName} ${lastName}`);

let firstName = "Svetlana";
let lastName = "Irinov";

console.log(`${firstName} ${lastName}`);

let firstName = "Sequina";
let lastName = "Rodriguez";

console.log(`${firstName} ${lastName}`);
```

The inefficiencies of this code are obvious - from needlessly repeating the same code, to the high probability of human error as we increase the number of times we need to perform the operation.

```js
let firstName = "Jessawynne";
let lastName = "Parker";

// Oops, I misspelled firstName. My program now has an error, or bug, in it.
console.log(`${fist_name} ${lastName}`);
```

When the same lines of code need to be repeated, even just once, then you put those lines of code in a function. You provide a name for a function, and it needs to be descriptive enough to understand what its purpose is.

```js
const displayName = (firstName, lastName) => {
  /*
    Since the code needed to display a person's name is written
    only once, we never have to worry about a developer
    misspelling a word, or missing a character because she
    needed to write the code for the 34th time.
  */
  console.log(`${firstName} ${lastName}`)
}

displayName("Jamal", "Haynes")
displayName("Debra", "Gordon")
displayName("Svetlana", "Irinov")
displayName("Sequina", "Rodriguez")
displayName("Jessawynne", "Parker")
```


## Challenge: Take a Number - Battle of the Bands

A local nightclub is having a Battle of the Bands night in a few months. They expect many bands to sign up because the grand prize is $20,000. To make things easier on the nightclub management, they want each band to be assigned a number so that they can easily keep track of the order in which the bands will perform.

Your job is to write a function that accepts any band name as an argument. The function will increment a global variable by one each time it is invoked, and display that number, and the band name concatenated together to the DOM.

```js
const bandNumber = 1

const takeNumber = function () {
  /*
    Write your awesome code here. See comments
    below for what should be returned.
  */
  printToDom(???, ????);  // you should already have this function written from the class lecture
};

takeNumber("Galactic Scum") // This should display "1. Galactic Scum" in the DOM
takeNumber("Underdogs") // This should display "2. Underdogs" in the DOM
```
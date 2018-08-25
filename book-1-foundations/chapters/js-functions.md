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

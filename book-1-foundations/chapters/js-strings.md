# Javascript Strings

Strings are exactly what they sound like - a bunch of text that renders exactly as it is saved.  They are important in JS because they are one of the five primitive types (string, number, boolean, null, undefined).  These primitive types are used to build up objects and arrays.

As a developer it will be important to understand how to manipulate strings to solve problems when trying to display data.  To do this we can use conditional statements, operators and string methods.

### Conditional Statements
Conditionals allow us to apply logic to certain expected values.  For example:
```js
const age = 34;
if (age < 21) {
  console.log('no drinks for you');
} else {
  console.log('PARTAY!!!!!');
}
```
In the above example we use the age variable to determine which statement to console out.  We could use similar logic to determine what content to print to the DOM based on a defined age.

### Operators
Operators allow us to determine if something is equal to something else.  Or if we want to check multiple things.  Most of these operators will return true or false.  Based on that response you can then do something.
#### Equality Operators
To check if something is equal we can use `==` or `===`.  It is better to always stick to `===` because this checks both the value and the type to make sure things are really exactly equal.
```js
console.log(1 === '3'); //false
```

#### Relational Operators
Checking if something is greater than or less than.
```js
console.log(1 < 5); //true
```

#### Logical Operators
Using AND, OR, and NOT logic.
```js
console.log(1===1 && 'cat'==='dog'); //false - cat not equal to dog
```

```js
console.log(1===1 ||'cat'==='dog'); //true because 1=1
```

```js
const a = true;
console.log(!a); //false
console.log(!!a); //true
```

### String Methods
Javascript has a TON of built in functions on the String constructor.  They all do slightly different things but can be super helpful.  Lets explore a few of them.
#### .length
The length method will tell you how long a string is - ie how many characters.
```js
console.log('cats'.length); // this should return 4 because there are 4 letters in cats
```

#### .indexOf
For a string this gives the starting position of the a group of characters.  If it doesn't find the group of characters it returns a `-1`.
```js
const quote = 'winter is coming';
console.log(quote.indexOf('is')); // 7 - the word 'is' starts on the 7th index
console.log(quote.indexOf('cow')); // -1 - the word 'cow' does not appear in this string
```

#### .charAt
Gives the character at a specific index.
```js
const quote = 'winter is coming';
console.log(quote.charAt(2)); // n
```

#### .replace
Exactly what it sounds like.  Replace a selection of text with something else.
```js
const quote = 'winter is coming';
const newQuote.replace(/is/g, "ain't");
console.log(newQuote); // winter ain't coming
```

# Challenge
Create a div with an id of `sonnet`.  In your JS file create the following variable:
```js
const sonnet = "How like a winter hath my absence been From thee, the pleasure of the fleeting year! What freezings have I felt, what dark days seen! What old December's bareness everywhere! And yet this time removed was summer's time; The teeming autumn, big with rich increase, Bearing the wanton burden of the prime, Like widow'd wombs after their lords' decease: Yet this abundant issue seemed to me But hope of orphans, and unfathered fruit; For summer and his pleasures wait on thee, And, thou away, the very birds are mute: Or, if they sing, 'tis with so dull a cheer, That leaves look pale, dreading the winter's near.";
```

Use the string methods we just covered to do the following:
* Find and output the starting position of the word "orphans". (use a console.log for this)
* Output the number of characters in the sonnet.(use a console.log for this)
* Replace the first occurance of the string "winter" with "yuletide".
* Replace all occurances of the string "the" with "a large".

Once you have the final string print it to the sonnet div.
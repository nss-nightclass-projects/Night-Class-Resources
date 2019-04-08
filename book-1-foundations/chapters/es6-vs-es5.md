# Javascript: ES6 vs ES5

## The History of Javascript
JavaScript was written in May 1995 in 10 days by Brendan Eich.  It was originally called Mocha but was later renamed to LiveScript.  Netscape purchased the trademark for JavaScript from Sun Microsystems and it was officially named JavaScript in December 1995.

It has the word Java in its name because that was a popular language at the time.  Other than sharing the same name there is absolutely no relationship between Java and JavaScript.

Sometime between 1996 and 1996 Netscape took JavaScript to the Ecma Standards organization which is why later versions are called ECMAScript 1, 2, 3, 5, 6, and 7.

## What is ES6?
ES5 or ECMAScript 5 was introduced in 2009.  It was the first JS release since 1999 so it was packed with a HUGE number of new features.  It included library support for JSON formatting, Array methods, and new Object methods to help with listing (for example Object.keys).  At this time ES5 is completely standard across ALL web browsers (except IE8 and older - they have some parts of ES5 but not all).

ES6 (or ES2015) stands for ECMAScript 6.  It was introduced in 2015 and was the first MAJOR JS release in 16 years.  It has major differences in the way JS is written that mostly exist to help the developers who write it.  At this point features of it are standard across many browsers but not all.  To find out if you can use an ES6 feature on a specific browser search for it [HERE](https://caniuse.com/).  There are transpilers out there like [Babel](https://babeljs.io/) and [Traceur](https://github.com/google/traceur-compiler) that allow you to write your code in ES6 and then compile the code down to ES5 so it will work with any browser.

## ES6 Methods we Will use Everyday
* const
* let
* Template Literals
* Arrow Functions
* Object Shorthand Notation

### const
Const is used for holding variables and complex objects that can not be re-assigned.  Think of it like a read only variable.  This is great for things like DOM references.

```js
  const selectedDiv = document.getElementById('cat');
```

### let
Let - short for Lexically scoped variables is a variable that only exists in the scope that it is defined in.  It can be re-assigned.

```js
if (testCondition){
	let fruit = ‘banana’;
	console.log(fruit); // banana
}
console.log(fruit) // undefined

```
### Template Literals
Template Literals make string concatenation extremely easy.  Instead of using `+` signs everywhere we can make use of `${}` to input variables.

Traditional String Concatenation:
```js
const name = “Rupert”;
const sentence = “Hello ” + name + “, welcome!”;
```
Template Literals:
```js
New Way
const name = “Rupert”;
const sentence = `Hello ${name}, welcome!`;
```

### Arrow Functions
Arrow functions are a simpler way of writing functions - you just don't write the word function.  There are certain cases were they don't work as expected - especially  when you are using `this`.  We will let you know when you can't use them.

Plain Functions:
```js
function writeToDom(string, id) {
	document.getElementById(id).innerHTML = string;
}

writeToDom(‘hello world!’, ‘input-id’);
```

Arrow Functions:
```js
const writeToDom = (string, id) => {
	document.getElementById(id).innerHTML = string;
}
writeToDom(‘hello world!’, ‘input-id’);
```

If you are feeling fancy and want to write them in one line you can remove some parenthesis:
```js
const greetingsArray = names.forEach(name => `Welcome to Hogwartz, ${name}`;
```

### Object Shorthand Notation
Object shorthand notation is a shorter way to construct objects.  It only works when you want to set a variable to a key and both the variable and key have the same name.

Old Way:
```js
let name = ‘Smitty’;
let score = 42;

let winner = {
	name: name,
	score: score
}
```

New Way:
```js
let name = ‘Smitty’;
let score = 42;

let winner = {
	name,
	score
}
```
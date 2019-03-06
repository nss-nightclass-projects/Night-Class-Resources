# Javascript Arrays
Arrays are like buckets of stuff where the order matters.  For example if we take a bucket and fill it with cats we should always know the order of the cats in the bucket;  something like:
```js
const cats = ['fluffy', 'spike', 'Mr. Whiskers', 'killer'];
```
The majority of the tasks you will accomplish in this course and in your dev career will involve looping over an array of objects and displaying that data to the DOM.

### Useful Array methods
#### Split
Split takes a string and breaks it into an array.  Each letter becomes its own indexi in the new array
```js
const bestFriend = “cow”;
const bestFriendArray = bestFriend.split(); //[“c”, “o”, “w”]
```
#### Join
Join takes an array and smashes all the indexes together into a string.
```js
const array2 = [“cow”, “dog”, “cat”];
const string2 = array2.join(‘,’); //”cow,dog,cat”
```

#### Pop
Removes the last index of an array.
```js
const animals = [“cat”, “dog”];
const lastAnimal = animals.pop(); // ”dog”
console.log(“animals”, animals); // [“cat”]
```

#### Push
Adds to the end of an array.
```js
let animals = [“cat”, “dog”];
animals.push(“bear”);
console.log(“animals”, animals); //[“cat”, “dog”, “bear”]
```

#### Shift
Removes from the front of an array.
```js
let animals = [“cat”, “dog”];
const first = animals.shift(); // “cat”
console.log(“animals”, animals); //[“dog”]
```

#### Unshift
Adds to the front of an array.
```js
let animals = [“cat”, “dog”];
animals.unshift(“bear”);
console.log(“animals”, animals); //[“bear”, “cat”, “dog”]
```
# JSON

## Introduction

JavaScript Object Notation, or JSON, is a language independent data format.  It was designed to allow for data transfer between servers and clients.  You can think of JSON as a javascript object with a minor difference - all the keys in the objects need to have double quotes around them.


## Data Types
JSON is built up as a series of key/value pairs.  The values must be one of the following types:
* **Number**: whole number, decimal, or using exponential E notation - no NaN allowed.
* **String**: any characters or spaces - must be surrounded with double quotes
* **Boolean**: true or false  -NO quotes
* **Null**: an empty value marked by `null` - no quotes needed
* **Object**: comma-separated,unordered list built up of key/value pairs
* **Array**: comma-separated,ordered list surrounded by square brackets. Each item in the list can be one of any of the types outlined in the above bullets.

Here is a sample JSON file:
```json
{
  "foods": [
    {
      "id": 1,
      "name": "Linguine",
      "category": "pasta",
      "ethnicity": "italian",
      "ingredients": ["noodles", "tomato sauce", "cheese"],
      "isFavorite": false,
      "calories": 1000
    },
    {
      "id": 2,
      "name": "Massaman curry",
      "category": "curry",
      "ethnicity": "thai",
      "ingredients": ["potatoes", "chicken", "curry powder"],
      "isFavorite": true,
      "calories": 10
    },
    {
      "id": 3,
      "name": "Green curry",
      "category": "curry",
      "ethnicity": "thai",
      "ingredients": ["bamboo shoots", "fish sauce", "veggies"],
      "isFavorite": false,
      "calories": 1000
    }
  ]
}
```

## JSON Tools
### JSON Linter
  Incorrectly formatted JSON doesn't work.  And often you can't tell from the browser what the problem with the file is.  Because of this you should run your json data through a linter before trying to work with it.  My personal favorite linter is [JSON Lint](https://jsonlint.com/).  Once you finish writing the file copy the entire contents into the text area on the site and click the Validate JSON button.  If you code is good it will say valid JSON.  If there are any errors it will tell you the last line that it successfully understood.  Start looking around that line to find your error.

### JSON Formatter
At this point almost all APIs return data in JSON format - there are a few older APIs that do this and you should seriously consider not using an API that doesn't provide data back in JSON.  APIs that don't return JSON often return XML which is extremely painful.

When getting data back from and API you typically get A LOT of data - and that can be hard to read.  Luckily there is a great Chrome Plugin called [JSON Formatter](https://chrome.google.com/webstore/detail/json-formatter/bcjindcccaagfpapjjmafapmmgkkhgoa) that will parse JSON data that is returned into an easier to read format - exactly what objects look like when they are console.logged into the chrome dev tools.

## JSON Utilities
JavaScript includes two main utility functions for JSON - parse and stringify.

When you get JSON data back from a server it will frequently be returned to you as a giant string.  This makes the data easy to transfer but is not very convenient for looping over.  To convert the JSON from a string to a regular JS object use the parse utility like this:
```js
const jsonString = "{"pets": [{"name":"Fluffy", "type":"cat"}, {"name":"Killer", "type":"bear"}, {"name":"Spot", "type":"fish"}]}";

const jsObject = JSON.parse(jsonString);
```

When you are taking data from the client side and transferring it to a server certain APIs require the data to be in a string format.  A great example of this is when you have a form that a user fills out and then you want to save the results of that form to firebase.  In order to convert a JS object to stringified JSON you can use the strinfigy utility like this:
```js
const jsObject = {a: 1, b: 2, c: 3};

const jsonString = JSON.stringify(jsObject);
```

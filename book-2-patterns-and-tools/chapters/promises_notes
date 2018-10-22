# Promises

Link to the [Slide Version](https://docs.google.com/presentation/d/1qaSIsUynsvKZ7fghujWL4qNFMMvQozaOnZAdfKmldVs/edit?usp=sharing)

Promises are the best way to deal with asynchronous code in javascript! ...now, what was asyc code again? it basically means dealing with any code that will take a long time to run. This will often happen when querying for information from an external datasource.

We have dealt with this problem in the past by using functions that execute after the XHR `load` has completed or the jQuery ajax has triggered `.done()`. Promises will follow that same essential pattern, but will give us a way to make that code more readable.

That's because Promises are essentailly **call-back function managers**.

They give us specific a method that gets called when data comes back successfully: `.then()` and method that gets called when something goes wrong: `.catch()`.

### Creating Promises

We're going to start using Promises in our code by constructing them ourselves. It will look something like:

```javascript
const myFirstPromise = () => {
  return new Promise((resolve, reject) => {
    // do something asynchronous with eventaully calls either
    //
    // resolve(someValue); // fulfilled
    // or
    // reject('failure reason'); // rejected
  })
}
```

We can then call this function when we want to be given this data. 

> Note: Various APIs will return promises to you. In that case, you will not need to create a Promise with the contstructor.

### Accessing Data from a Promise

The `.then()` method will expose a function where you can use the data successfully fulfilled by the Pormise. The `.catch()` method will expose a function where you can handle the error message returned. Either one or the other will trigger for a Promise -- never both.

### Promise chaining and other patterns

Promise Chaining: useful when you need to get some data before you get others. It will follow this general pattern:

```javascript
newPromise()
  .then((d1) => {
    return secondPromise();
  })
  .then((d2) => {
    return thirdPromise();
  })
  .then((d3) => {
    doSomething();
  })
  .catch((error) => {
    console.error(error);
  })
```

Promise.all() will run multiple promises in parallel. It is especially useful when trying to aggregate together similarly structured data.

```javascript
Promise.all([promiseOne(), promiseTwo(), promiseThree()])
  .then((allTheData) => { 
    // allTheData is an array that contains the results for the promises in their corresponding indexes
    const allDataArray = [...allData[0], ...allData[1], ...allData[2];
  })
  .catch(error => console.error('this will trigger if there is an error thrown by any of the promises'));
```

> Note on chaining: You can also pass resolved data into the function holding the constructor for another promise, i.e. `secondPromise(d1)`

### General Steps for using Promises

1. Does the place i’m getting data from return a promise?
  a. Yes - then resolve it.
  b. No, go to step 2
2. Do I need multiple promises?
  a. No - use a single promise constructor
  b. Yes, go to step 3
3. Do my promises need to chain? (do i need data from one before I get data from the 2nd)
  a. Yes - chain those promises
  b. No - use that promise.all() magic

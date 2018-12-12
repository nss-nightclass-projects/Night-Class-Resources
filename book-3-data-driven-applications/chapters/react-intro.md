# Intro to React
Now that we have created our repo using create-react-app and modified the file structure to fit our needs, its time to take a deeper look at what we have and how things work.

## JSX
Things to know: 
- You must always have one main container (one parent tag) for all of the tags created.
- We will write JSX to be returned from our component's render method. Multi-line JSX can be written if you include parenthesis around the JSX:
```
render() {
  return (
    <div className="GreetingComponent">
      <h1>Hello World!</h1>
    </div>
  )
}
```
Parenthesis are not needed if you are returning only one line of JSX.

## What is class?/What is constructor?
fancy function - ok article [here](https://medium.com/javascript-scene/javascript-factory-functions-vs-constructor-functions-vs-classes-2f22ceddf33e)
## Why we are not using constructors?
tldr; ES6+
[Great Article](https://hackernoon.com/the-constructor-is-dead-long-live-the-constructor-c10871bea599)

## How to translate a constructor based class to what we are doing?

what is JSX

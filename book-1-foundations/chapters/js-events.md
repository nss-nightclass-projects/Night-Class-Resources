# Handling Browser Events with JavaScript

## Event based programming

Modern web application are becoming more and more event based rather than procedural. When a user performs any kind of gesture (click, key press, mouse over, etc.), the JavaScript layer will listen for that event and then perform some appropriate logic.

### index.html

```html
<header id="page-header">
  <h1>Page title</h1>
</header>

<ul>
  <li>Unordered list item 1</li>
  <li>Unordered list item 2</li>
  <li>Unordered list item 3</li>
</ul>

<article>
  <section class="article-section">Introduction</section>
  <section class="article-section">Body</section>
  <section class="article-section">Conclusion</section>
</article>

<input type="text" id="keypress-input">

<div id="output-target"></div>

<div id="guinea-pig">Leave me alone</div>
<button id="add-color">Add color</button>
<button id="make-large">Hulkify</button>
<button id="add-border">Capture it</button>
<button id="add-rounding">Rounded</button>
```

### eventHandlers.js

```js
var outputEl = document.getElementById("output-target")

/*
    You can get a reference to DOM elements and
    directly attach an event handler. In this
    example, we get every element with a class of
    "article-section" and listen for when the
    user clicks on the element. When that event
    fires, the attached "handleSectionClick"
    function gets executed.
 */
var articleEl = document.getElementsByClassName("article-section")

/*
    JavaScript, in the browser, automatically send the source
    event to the handler function for the event.
*/
function handleSectionClick (event) {
    console.log(event)
}

for (var i = 0; i < articleEl.length; i++) {
    articleEl[i].addEventListener("click", handleSectionClick)
}

/*
    Define functions that hold logic to be performed when mouse
    events are triggered by the browser.
*/
function handleHeaderMouseOver (event) {
    outputEl.innerHTML = "You moved your mouse over me"
}

function handleHeaderMouseOut(event) {
    outputEl.innerHTML = "Why u leave me?"
}

/*
    Get a reference to the DOM element with an id of
    "page-header", and attach an event handler for the
    mouseover, and mouseout, events.
 */
header.addEventListener("mouseover", handleHeaderMouseOver)
header.addEventListener("mouseout", handleHeaderMouseOut)



/*
    We can also write an anonymous function (lamba expression)
    in the addEventListener declaration instead of using a
    function reference.
 */
var fieldEl = document.getElementById("keypress-input")

fieldEl.addEventListener("keyup", function (event) {
    outputEl.innerHTML = event.target.value
})


/*
  Now we can start making a truly interactive experience
  combining HTML, JavaScript and CSS. When a user clicks
  on a button in the DOM, we can listen for that event in
  JavaScript, and then add, or remove, CSS classes.

  In this example, I simply use the `toggle()` method on
  the `classList` property of a DOM element to automatically
  add and remove a class.
 */
var guineaPig = document.getElementById("guinea-pig")

function toggleClass (newClass) {
  guineaPig.classList.toggle(newClass)
  console.log("guineaPig.classList", guineaPig.classList)
}

document.getElementById("add-color").addEventListener("click", function() {
    toggleClass("blue")
})

document.getElementById("make-large").addEventListener("click", function() {
    toggleClass("large")
})

document.getElementById("add-border").addEventListener("click", function() {
    toggleClass("bordered")
})

document.getElementById("add-rounding").addEventListener("click", function() {
    toggleClass("rounded")
})


/*
  EVENT BUBBLING:

  You can add an event handler on the body tag, and since all
  browser events bubble up to the body, you can then put in
  conditional logic to handle the click event on many different
  elements in one function.
 */
document.querySelector("body").addEventListener("click", function(event) {
    console.log("You clicked on the body of the DOM")
})
```

## Videos to Watch

1. NSS Learning Team video [Basic JavaScript Event Listeners](https://www.youtube.com/watch?v=4XvM096cQF4&list=PLX0ucpUE_qIOUsxGNEPpP9yonb4zerVIC&index=3)
1. NSS Learning Team video [JavaScript Event Listener Types](https://www.youtube.com/watch?v=5zlueGaybjc&index=4&list=PLX0ucpUE_qIOUsxGNEPpP9yonb4zerVIC)

## Practice

Setup the following files.

> index.html

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>Nashville Software School</title>
</head>

<body>

  <article id="powerList">
    <section id="flight" class="power disabled">
        Flight
    </section>
    <section id="mindreading" class="power disabled">
        Mind Reading
    </section>
    <section id="xray" class="power disabled">
        X-ray Vision
    </section>
  </article>

  <button id="activate-flight">Activate Flight</button>
  <button id="activate-mindreading">Activate Mind Reading</button>
  <button id="activate-xray">Active X-ray Vision</button>

  <button id="activate-all">Active All Powers</button>
  <button id="deactivate-all">Deactive All Powers</button>


  <script src="powers.js"></script>
</body>
</html>
```

In the code below...

1. Replace the word `event` in the `addEventListener` method with the appropriate string to handle a click event
1. Write a function named `handlerFunction` that will remove the `disabled` class on the corresponding `<section id="flight">` (section, not button) and replace it with a class of `enabled`.
1. Have your developer tools open. When you click the button, the following element...

```html
<section id="flight" class="power disabled">
```

Should then look like this.

```html
<section id="flight" class="power enabled">
```

> powers.js

```js
document.querySelector("#activate-flight").addEventListener(event, handlerFunction)
```

Once you have that working, write two JavaScript statements for handling the click event on the other two buttons. Those event handlers should perform the same step of removing `disabled`, and adding `enabled` on the corresponding `<section>` elements

```js
document.querySelector("#activate-mindreading").addEventListener()
document.querySelector("#activate-xray").addEventListener()
```

Once that is complete, add two more buttons

1. Enable All Powers
1. Disable All Powers

Write two more event handlers for activating and deactivating **_all_** powers when the corresponding buttons are clicked. You will need to use the `document.querySelectorAll()` method for these.

> **Googling Tip:** [Adding classes to DOM components](http://lmgtfy.com/?q=javascript+add+class+to+DOM+element)

> **Googling Tip:** [Iterating over DOM components identified with querySelectorAll](http://lmgtfy.com/?q=iterating+over+elements+querySelectorAll)


### One Step Further
You may notice that your code to enable individual powers (not all at once) is very similar. To keep your code DRY, make one function that will handle activating a power depending on which button is clicked. (Hint: one way to get started is to use `event.target.id.split("-")` in your function)

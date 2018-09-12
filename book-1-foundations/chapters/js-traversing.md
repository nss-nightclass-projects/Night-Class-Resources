# Traversing the DOM in JS

## Viewing your page as a tree:



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

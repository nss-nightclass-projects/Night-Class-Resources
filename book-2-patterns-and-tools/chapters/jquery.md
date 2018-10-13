# jQuery
> [Link to Slide Version](../images/jQuery.pdf)

## What is jQuery?
> A JavaScript library (some people wrote some JavaScript that makes it easier for other developers to write JS)

**Primary goals:**
- DOM manipulation
- DOM Events
- AJAX / Data retrieval
- Effects & animation
- Multi-browser support

Yes, it is old school. But also:
> jQuery is used by 96.1% of all the websites whose JavaScript library we know. This is 73.4% of all websites.

Once we learn jQuery, we will basically be deprecating these from our life:
- `document.getElementBy…`
- `.addEventListener`
- `element.innerHTML = ...`
- `.parentNode.parentNode.children[0]`
- `classList.contains`
- `new XMLHttpRequest()`

<hr>

## jQuery Selectors

jQuery basic syntax selects a dom element and then performs some action:
`$("selector").action()`

jQuery selects all <p>’s and then hides them all
`$("p").hide()`

jQuery uses CSS syntax to “find” and select HTML elements based on their name, id, classes, types, attributes, values of attributes, etc.
```js
$("#main") // gets the element with ID of 'main'
$(".fancy") // gets a list of elements with class of 'fancy'
$("p") // gets a list of elements with 'p' tag
$("div.fancy") // gets a list of all divs with class 'fancy'
 ```

**Old Way:**
`const childrenOfMain = document.getElementById("main").getElementsByClassName("child")`

**New Way:**
`const childrenOfMain = $("#main .child”)` 🎉

#### In Class Challenge: What would the jQuery selector be to target all of the bananas with the class ‘funky’
```
<div>
	<h1 class=‘funky’> Monkey </h1>
	<div>
		<banana class=‘funky’> Bernerner </banana>
		<banana class=‘funky large’> B A N A N A </banana>
		<banana> Banana </banana>
	</div>
	<banana class=‘funky’> 100 </banana>
</div>
```

### Getting Attribute
So, jQuery has a bunch of different methods that allow you to both GET and SET values of HTML elements
```
$( "#main" ).html(); // GETS the HTML content of the div main

$( "#main" ).html('<p>Sample</p>'); // SETS the HTML content of the div main
```

You can also use .val(), .text(), .height(), and various other methods to quickly get information from an HTML element or set it to new values.

## Events
The new and improved way of adding event listeners

### jQuery Basic Events
jQuery makes it drastically easier to listen for events on the DOM

```
$("#button").click((e) => {
	console.log(e);
});

const logEvent = (e) => {
	console.log(e);
}


$("#button").click(logEvent);
```
### jQuery Common Events

Here are some of the methods that you will most commonly use to attach events with jQuery:
Mouse events: .click(), .hover(), .mouseleave()
Keyboard events: .keyup(), .keypress()
Form events: .change(), .select(), .submit()
Event handler attachment: .on() 

Let’s talk more about this .on() ...

### jQuery .click() vs .on()

.click() works perfectly well until it doesn’t...

It will not work for elements that are loaded into the DOM after jQuery has loaded. For example, anything that is printed dynamically with our printToDom function. For those cases, we need to use .on()

```
$(".dynamic-button").on("click", (e) => {
  console.log(e);
});
```

### Attaching Event Listeners to many DOM elements

Old Way: 
```
const children = document.getElementsByClassName("child");

for (let i = 0; i < children.length; i++) {
	children[i].addEventListener('click', myEvent);
}
```

New Way:
```
$(".child”).on('click', myEvent)
```

## Traversing the DOM
Methods to navigate your dom tree and also to filter through those results

### Common Methods
Going up the tree:
```
.parent() // returns the direct parent
.closest('.fancy') // returns the closest parent with the class of fancy
```

Going down the tree
```
.children() // returns the list of direct children
.find('.fancy') // returns the closest descendant with the class of fancy
```
Going sideways? the tree: Well said Callan well said....

```
.siblings() // returns the list of any siblings in the DOM
```

### Bonus Methods
You can use ‘show’, ‘hide’, and ‘toggle’ to control the display of your html elements:

```
$('.crap .child').hide(); // hides all of the elements with class ‘child’ that are children of the parent with the class ‘crap’
```

### Wrapping non-jQuery elements up to use jQuery methods

Sometimes you will have methods that return non-jQuery enabled DOM elements, for example: event.target. You will need to wrap them in the jQuery syntax in order to use jQuery methods on it.

```
$('.crazy button').on('click', (event) => {
	$(event.target).hide()
});
```



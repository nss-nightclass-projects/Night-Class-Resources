# jQuery
> [Slides to powerpoint](../images/jQuery.pdf)

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

##

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

## jQuery Selectors

jQuery basic syntax selects a dom element and then performs some action:
`$("selector").action()`js

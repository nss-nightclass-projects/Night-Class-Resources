# Tooling For HTML and CSS

## VSCode
// TODO: description of an editor here.

### Emmet
Emmet support is built right into VS Code. You can type CSS-like expressions that can be dynamically parsed, and produce output depending on what you type in the abbreviation. Emmet is developed and optimised for web-developers whose workflow depends on HTML and CSS.

#### Emmet Abbreviations
[A complete cheatsheet](https://docs.emmet.io/cheat-sheet/)

*Element:* `div` => 
```<div></div>```

*Child:* `ul>li` => 
```
<ul>
  <li></li>
</ul>
```

*Sibling:* `div+p+bq` => 
```
<div></div>
<p></p>
<blockquote></blockquote>
```

*Multiplication:* `ul>li*5` =>
```
<ul>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
</ul>
```

*Adding an Id or Class:* `ul#my-list>li.list-item*5` =>
```
<ul id="my-list">
    <li class="list-item"></li>
    <li class="list-item"></li>
    <li class="list-item"></li>
    <li class="list-item"></li>
    <li class="list-item"></li>
</ul>
```
Emmet also has [abbreviations for CSS](https://docs.emmet.io/css-abbreviations/) if you are into that!

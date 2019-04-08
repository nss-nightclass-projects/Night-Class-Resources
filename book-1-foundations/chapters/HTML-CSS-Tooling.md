# Tooling For HTML and CSS

## VSCode
Source code editors have features specifically designed to simplify and speed up typing of source code, such as syntax highlighting, indentation, autocomplete and brace matching functionality. These editors also provide a convenient way to run a compiler, interpreter, debugger, or other program relevant for the software development process. So, while many text editors like Notepad can be used to edit source code, if they don't enhance, automate or ease the editing of code, they are not source code editors.

Visual Studio Code combines the simplicity of a source code editor with powerful developer tooling, like InteliSense code completion and debugging.

First and foremost, it is an editor that gets out of your way. The delightfully frictionless edit-build-debug cycle means less time fiddling with your environment, and more time executing on your ideas.

#### Extensions to Install:
1. [HTML & CSS Class Complete](https://marketplace.visualstudio.com/items?itemName=Zignd.html-css-class-completion)
1. [CSS Code Peek](https://marketplace.visualstudio.com/items?itemName=pranaygp.vscode-css-peek)
1. [Auto Rename Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag)
1. [Material Icons](https://marketplace.visualstudio.com/items?itemName=PKief.material-icon-theme) (this one is just because I like it 💁)

#### Formatting
VS Code has great support for source code formatting.:
- Format Document (⇧⌥F) - Format the entire active file.

### Emmet
Emmet support is built right into VS Code. You can type CSS-like expressions that can be dynamically parsed, and produce output depending on what you type in the abbreviation. Emmet is developed and optimized for web-developers whose workflow depends on HTML and CSS.

#### Emmet Abbreviations
[A complete Cheat Sheet](https://docs.emmet.io/cheat-sheet/)

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

# Enable SCSS
By default React comes with regular CSS but only amateurs write real CSS.  Real developers (like us) like to write SCSS.

## Installation

1.  Install the node-scss package

```shell
npm install node-sass --save-dev
```
2.  Rename `index.css` to `index.scss`
3.  In `index.js` update the import statement to `import './index.scss';`
4.  Rename `App.css` to `App.scss`
5.  In `App.js` update the import statement to `import './App.scss';`

## Make a global styles folder

We will need somewhere to hold our _variables.scss and other global styling files.
1. Make a folder inside src called styles (`src/styles`).
2. Move index.scss into the styles folder
3. Correct the import statement in index.js so it is:
`import './styles/index.scss';`
4. Create `src/styles/_variables.scss` and add the following:
```scss
$favColor: red;
```
5. Replace the contents of `src/styles/index.scss` with the following
```scss
@import 'variables';

body {
  background-color: $favColor;
}
```


[Return to Instructions](../react-setup.md)
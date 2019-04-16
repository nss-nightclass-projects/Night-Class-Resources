# Running Webpack
Before we start webpack we need to create some files.  Otherwise we will get some errors.  There is no need to add script or link tags for any of these files - webpack will do that for you.

## index.html
First we need to make an index.html.  This file need to live at `src/index.html`.  It should have some boilerplate code:
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Test</title>
</head>
<body>
  
</body>
</html>
```

# main.scss
Since we are no longer writing in css we need to creat a main.scss file.  This file should live in `src/styles.main.scss`.  In this file change the background color of the body.
```css
body {
  background-color: blue;
}
```

## main.js
Next we need a main.js file because that is the entrypoint to our application.  This file should live at `src/javascripts/main.js`.  Since we can no longer add `console.log` statements add a `console.error` so we can see if things are working correctly.  We also need to import main.scss.
```js
import '../styles/main.scss';

console.error('hi');

```

## Just run the dang thing
Lets try running webpack!  We have created two scripts in our `package.json` file - they look like this:
```js
"scripts": {
  "start": "webpack-dev-server --mode development --open",
  "build": "webpack --mode production --module-bind js=babel-loader"
}
```
The scripts section of the package.json file is where you can write custom mini scripts to alias complex tasks - so we don't have to remember the complex parts.

### Development Mode
The top script is for development mode.  It starts the webpack development server (ie instead of making a physical build folder it makes that in memory).  To run this script type `npm start`.  This will start webpack and keep it running.  It will automatically open a browser to the correct url and your terminal will continuously update as you make code changes.

### Production Mode
The bottom script creates a production build of your code.  To run webpack in this way type `npm run build`.  After webpack finishes it will exit out to the command line and you should now see a folder called `build`.  This folder is now ready to be deployed the internet.  You should only need to run this version of webpack when you want to deploy stuff.  We will talk about how to deploy stuff in a few weeks.


## Running Webpack
Lets try running webpack!  We have created two scripts in our `package.json` file - they look like this:
```js
"scripts": {
  "start": "webpack-dev-server --mode development --open",
  "build": "webpack --mode production --module-bind js=babel-loader"
}
```
The scripts section of the package.json file is where you can write custom mini scripts to alias complex tasks - so we don't have to remember the complex parts.

The top script is for development mode.  It starts the webpack development server (ie instead of making a physical build folder it makes that in memory).  To run this script type `npm start`.  This will start webpack and keep it running.  It will automatically open a browser to the correct url and your terminal will continuously update as you make code changes.

The bottom script creates a production build of your code.  To run webpack in this way type `npm run build`.  After webpack finishes it will exit out to the command line and you should now see a folder called `build`.  This folder is now ready to be deployed the internet.  You should only need to run this version of webpack when you want to deploy stuff.  We will talk about how to deploy stuff in a few weeks.
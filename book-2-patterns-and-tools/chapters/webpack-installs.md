# Webpack Installs

## npm installs
### Package.json
To install 3rd party libraries we will be using npm for the duration of class.  To get started you need to initialize your project as one that uses npm.  Run the following command:
```js
npm init -y
```

This command should create a file called package.json in the root of your project.  The file should look something like this:
```json
{
  "name": "new-repo",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC"
}
```

Now that we have made the file we can go in and modify it using vs code.  Change the main, scripts, author, and liscense values in your package.json file to look like this:

```json
{
  "name": "new-repo",
  "version": "1.0.0",
  "description": "",
  "main": "src/javascripts/main.js",
  "scripts": {
    "start": "webpack-dev-server --mode development --open",
    "build": "webpack --mode production --module-bind js=babel-loader"
  },
  "keywords": [],
  "author": "Zoe Ames",
  "license": "MIT"
}
```

This file is where we will save references to the packages we are going to use in the project.  This allows future users to install what they need to get things running.  There are two types of ways we will save things - dev dependences and regular dependencies.

Dev dependences are for things that are required in order to develop the code.  In our case that is all things webpack.

Regular dependences are things that are required to be installed in order for the code to run.  In our case that will be things like Jquery and Boostrap.

### Installing Dev Dependencies
To install the dev dependences we need run the following line of code:
```sh
npm install @babel/core @babel/preset-env babel-loader css-loader eslint eslint-config-airbnb-base eslint-loader eslint-plugin-import file-loader html-loader html-webpack-plugin mini-css-extract-plugin node-sass sass-loader webpack webpack-cli webpack-dev-server --save-dev
```
After you do this you will see that you should now have a folder called node_modules with a BUNCH of stuff in it.

If you take a look at your package.json file you should see a section called devDependencies that includes a list of all the packages we just installed.  Our package.json file knew to put these things as dev dependencies because at the end of the line we have a `--save-dev`.

After doing the installs you should also see a file called package-lock.json.  This file keeps track of the EXACT version numbers that got installed.  It also keeps track of any dependences of your dependencies and their exact versions.

## .gitignore
Now that we are compiling our code and installing third party packages we need a way to keep our projects from pushing up code that does not belong to us.  To do this we create a file called .gitignore that goes at the root of our project.  This file tells git to NOT track anything inside it.  We will add the following files:
```sh
.vscode/
package-lock.json
node_modules/
dist/
build/
```

What are these things we are ignoring?

The `node_modules` folder is where all the third party libraries we are going to install live.  Since this is not our code we don't want to push it up to github.  People who decide to download the project and run it can install the stuff directly from our package.json file.

The `package-lock.json` file is used to track what specific version of each package you are using.  Unless you are working on a complex production level application it isn't really needed and tends to add a lot of extra info to PRs.

The `dist` and/or `build` folders are created by webpack when you create a production build of your code.  They are minified and ugified versions of the existing code - ie a smaller duplication.  We don't need to push this because we are pushing the real code.

## Babel Configuration
Create a file called `.babelrc` at the root of your project.  Add this to that file:
```js
{
  "presets": [
      "@babel/preset-env"
  ]
}
```
This file tells babel how to convert the JS in our project. We are using `@babel/preset-env` which is a preset list of ES6+ to ES5 conversion rules created by the babel team.  Their list is very thorough so no reason for us to reinvent the wheel and make our own conversion rules.

## Eslint Configuration
We will need to create 2 eslint configuration files.  More information on these two files and what goes in them is in the [Eslint section](./webpack-eslint.md).

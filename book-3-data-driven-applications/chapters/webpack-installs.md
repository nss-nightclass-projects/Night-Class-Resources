# Webpack Installs

## npm init
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

This file is where we will save references to the packages we are going to use in the project.  This allows future users to install what they need to get things running.  There are two types of ways we will save things - dev dependences and regular dependencies.

Dev dependences are for things that are required in order to develop the code.  In our case that is all things webpack.

Regular dependences are things that are required to be installed in order for the code to run.  In our case that will be things like Jquery and Boostrap.

## Installing Dev Dependencies
To install the dev dependences we need run the following line of code:
```sh
npm install babel-core babel-loader@7 babel-preset-env css-loader eslint eslint-config-airbnb-base eslint-loader eslint-plugin-import extract-text-webpack-plugin html-webpack-plugin node-sass sass-loader style-loader webpack webpack-dev-server --save-dev
```
After you do this you will see that you should now have a folder called node_modules with a BUNCH of stuff in it.

If you take a look at your package.json file you should see a section called devDependencies that includes a list of all the packages we just installed.  Our package.json file knew to put these things as dev dependencies because at the end of the line we have a `--save-dev`.

## Installing Regular Dependencies
To install the front-end dependences run the following:
```sh
npm install bootstrap jquery popper.js --save
```
You should now see these three packages under the dependencies object in the package.json file.  Our package.json file knows to save this stuff as regular dependencies because of the `--save` flag at the end of the line.

After doing the installs you should also see a file called package-lock.json.  This file keeps track of the EXACT version numbers that got installed.  It also keeps track of any dependences of your dependencies and their exact versions.

## .gitignore
The node_modules folder is FILLED with code that is not ours.  Because of this we don't want to push that code up to our github repo.  People who decide to download the project and run it can install the stuff directly from our package.json file.  To keep the node_modules from getting to github we need to make a file called .gitignore at the root of the project and put the following code in it:
```sh
node_modules/
```





EDITS for windows:
https://www.npmjs.com/package/win-node-env

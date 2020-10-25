# Setting up React
To set up react we will be using a scaffolding tool called [Create React App](https://github.com/facebook/create-react-app).

[Intro Video](https://www.screencast.com/t/ayjiMtnasAeY)

## What is create-react-app?
create-react-app is a tool built by facebook that quickly sets up a React project.  The project was built with three main goals:
1. one dependency (webpack does all the things)
2. No configuration required (standard reasonable configurations for development and production builds)
3. no lock-in (if you don't like the standard configuration you can eject and create your own)

Out of the box we will be able to enjoy the following great features:
* REACT with JSX
* ES6+ (all the es6 stuff we love writing with)
* Autoprefixes CSS (no need to add in all the -webkit stuff)
* Unit test runner (Jest is already installed and configured)
* Live development server (make some changes and the app automatically reloads)
* Build scripts to bundle all the things (JS, CSS, images, and sourcemaps)
* Offline service works (you can *technically* do development offline)
* Hassle free updates (if a new version of create-react-app comes out you just update the version in the package.json file)

## Chrome Extension
- Install the extension [React Developer Tools](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en). This will show up in your **dev tools** in the top bar (but only when you are viewing a website that is using react)

## NEW REACT SETUP STEPS

[Walkthrough Video](https://www.screencast.com/t/jJVYX4VK)

Follow all theses steps (in the order listed) to get your new project up and running:
1. [Create a new local react project](./react-setup-steps/local-project.md)
1. [Github](./react-setup-steps/github-setup.md)

Create a setup branch and do all the following steps on that branch
1. [Remove Testing](./react-setup-steps/kill-testing.md)
1. [Enable SCSS](./react-setup-steps/add-scss.md)
1. [Move Files](./react-setup-steps/move-files.md)
1. [Add Eslint](./react-setup-steps/add-eslint.md)
1. [Add Front End Dependencies](./react-setup-steps/add-fontend-dependencies.md)
1. [Update App.js](./react-setup-steps/react-classes.md)

Try it all out: `npm start`

if it all looks good you can push everything up to github and merge your setup branch in.

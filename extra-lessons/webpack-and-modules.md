# Webpack and Modules

The goal of this lesson is to show how to create a new webpack instance from the webpack template, move code over from one project to another, and then modularize the code.

## Get Started
- Navigate to your Cohort Organization in Github
  - EXAMPLE: [nss-evening-cohort-14](https://github.com/nss-evening-cohort-14)
- Go ahead and pull up the sample [Sorting Hat Project](https://github.com/drteresavasquez/sorting-hat) for use later
- Find in the 'Pinned repositories', the `webpack-template` repo
- Watch the video to follow along

## VIDEOS:
- [Part 1: Setting Up Webpack (~ 8 minutes)](https://vimeo.com/512633280/c539450270) - Using the template and getting it running on your machine
- [Part 2: Walk through what is up! (~ 11 minutes)](https://vimeo.com/512648178/8a99b2600b) - Stepping through the readme and learning about the new environment
- [Part 3: Let's talk about this new stuff (~ 8 minutes)](https://vimeo.com/512659400/be86462f5c) - Talking through the structure of our project and some important files
- [Part 4: Rubber...meet the road (~ 8 minutes)](https://vimeo.com/512681084/fba98f6062) - Adding stuff to our app and ERROR ERROR EVERYWHERE!!!!
  - Pull up the [Sample Sorting Hat Project](https://github.com/drteresavasquez/sorting-hat)
  - Copy/paste stuff from Sorting Hat in this order while watching terminal for errors
    - index.html: https://github.com/drteresavasquez/sorting-hat-webpack/blob/main/src/index.html
    - remove all CDNs and links to external js and css from index.html
    - css file: https://github.com/drteresavasquez/sorting-hat-webpack/blob/main/src/styles/main.scss
    - js file...watch that terminal light up red like it is christmas!: https://github.com/drteresavasquez/sorting-hat-webpack/blob/main/src/javascripts/main.js


## Assignment 1 - Stop the BLOOD!!!
- Fix your errors:
  - Read each error
  - check the line number
  - if you are not sure what the error means, google it.
  - if you still cannot fix it, take a note and move on to the next error
- When your terminal is green, your app should run just as it did outside of webpack YAY!!
- If you have errors that may have been more cryptic in nature we will walk through errors as a class.

## Assignment 2 - Modules
- Video Starter

1. Get everything out of the HTML page. The only thing that should be in there is the body tag - create a component for all the stuff that was in the HTML file.
1. move all other functions into their own files and import/export as needed. The only thing in `main.js` should be the index page load and the button events load like this:
```javascript
import initialScreen from './components/intialScreen';
import domEvents from './helpers/domEvents';

import '../styles/main.scss';

const init = () => {
  initialScreen();
  domEvents();
};

init();
```


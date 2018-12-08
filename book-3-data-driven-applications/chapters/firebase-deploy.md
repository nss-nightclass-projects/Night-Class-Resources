# Deploying Your Project With Firebase

> Globally install the Firebase tools on your machine

`npm install firebase-tools -g`

`firebase login`
> run `firebase login --interactive` if you are getting the error `Error: Cannot run login:ci in non-interactive mode.`

:warning: Windows users ... might have to use powershell :skull:

## If Your Project Uses Webpack:
1. [Once per project] Update the scripts section of your package.json to include a deploy script:
```json
"scripts": {
    "build": "NODE_ENV=production webpack",
    "lint": "eslint ./src --ext .js --fix",
    "dev": "NODE_ENV=development webpack-dev-server --content-base dist --hot",
    "start": "npm run lint && npm run dev",
    "deploy": "npm run build && firebase deploy"
  },
```
2. [Once per project] Create a Firebase project (if you don't already have one for the database, Firebase will cap it at 5, BUT it will also let you create more if you request them and mention you are in school).
3. [Once per project] Run `firebase init`
    * Select 'hosting' using your arrow keys, hit the space bar and hit enter
    * Project Setup > select the project using your arrow keys, hit the space bar and hit enter
    * What do you want to use as your public directory? (public) > type `dist` and hit enter
    * Configure as a single-page app (rewrite all urls to /index.html)? (y/N) > type `y` and hit enter
    * IF it asks you if you want to overwrite > type `n` and hit enter
4. [Every time you have a major update you want to release] `npm run deploy`

## If Your Project Is Just Vanilla JS
1. [Once per project] Nest all of your project in a directory named 'public' EXCEPT for the README and any screenshots for the README. EG:
```
- public/
  |-index.html
  |-js/
    |-stuff.js
    |-main.js
  |-main.css
- README.md
- screenshots/
```
2. [Once per project] Create a Firebase project (if you don't already have one for the database, Firebase will cap it at 5, BUT it will also let you create more if you request them and mention you are in school).
3. [Once per project] Run `firebase init`
    * Select 'hosting' using your arrow keys, hit the space bar and hit enter
    * Project Setup > select the project using your arrow keys, hit the space bar and hit enter
    * What do you want to use as your public directory? (public) > type `public` and hit enter
    * Configure as a single-page app (rewrite all urls to /index.html)? (y/N) > type `n` and hit enter
4. [Every time you have a major update you want to release] `firebase deploy`

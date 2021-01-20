# Deploying Your Project With Firebase

You have two deploy options. You can deploy with Firebase or Netlify. These instructions are to deploy with Firebase. To deploy using Netlify, find the instructions [here](https://github.com/nss-nightclass-projects/REACT-Deployment-Netlify)

## Get Started with Firebase Deploy
1.  Globally install the Firebase tools on your machine (1x per machine)

`npm install firebase-tools -g`

NOTE: if after global installation, you have issues, you can run `npm install firebase-tools` in your specific project. If you run into permissions errors, use `sudo` before the command.

2.  Log into your firebase account via google (1x per machine unless you get logged out)
`firebase login`

:warning: Notes for windows users:
* Use the integrated terminal in VS Code
* If you are getting this error: `Error: Cannot run login:ci in non-interactive mode.` run the following command `firebase login --interactive`

## If Your Project Uses Webpack:
### Firebase Setup:
1. Update the scripts section of your package.json to include a deploy script:
```json
"scripts": {
    "deploy": "npm run build && firebase deploy"
  },
```
2. Create a Firebase project (if you don't already have one for the database, Firebase will cap it at 5, BUT it will also let you create more if you request them and mention you are in school).
3. Run `firebase init`
    * Select `hosting` using your arrow keys, **hit the space bar and hit enter**
    ```
    SAMPLE OUTPUT:
    ? Which Firebase CLI features do you want to set up for this folder? Press Space to select features, then Enter to confirm your choices. 
    Hosting: Configure and deploy Firebase Hosting sites
    ```
    * Please select an option: using your arrow keys select **Use an existing project**
    ```
    SAMPLE OUTPUT:
    === Project Setup
    ? Please select an option: Use an existing project
    ? Select a default Firebase project for this directory: fir-cows-958ae (firebase-cows)
    i  Using project fir-cows-958ae (firebase-cows)
    ```
    * Project Setup > select the project using your arrow keys, hit the space bar and hit enter
    * What do you want to use as your public directory? (public) > type `build` and hit enter
    * Configure as a single-page app (rewrite all urls to /index.html)? (y/N) > type `y` and hit enter
    ```
    SAMPLE OUTPUT:
    === Hosting Setup
    ? What do you want to use as your public directory? build
    ? Configure as a single-page app (rewrite all urls to /index.html)? Yes
    ✔  Wrote build/index.html

    i  Writing configuration info to firebase.json...
    i  Writing project information to .firebaserc...

    ✔  Firebase initialization complete!
    ```
    * **IF it asks you if you want to overwrite > type `n` and hit enter**
4. run `npm run deploy`
5. Modify your `.gitignore` - add the firebase folder `.firebase/`

### After Changes are made
So you made some cool new changes to your project.  You did a PR and merged everything to master.  How do you get those changes deployed to firebase?  Easy!  Locally switch to master and pull down the changes.  Then run `npm run deploy`.  Then check that your changes are there.  Firebase does do some caching so if you don't see your changes clear your cache and look again.

## If Your Project Is Just Vanilla JS
### Setup
1.  Nest all of your project in a directory named 'public' EXCEPT for the README and any screenshots for the README. EG:
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
2. Create a Firebase project (if you don't already have one for the database, Firebase will cap it at 5, BUT it will also let you create more if you request them and mention you are in school).
3. Run `firebase init`
    * Select `hosting` using your arrow keys, hit the space bar and hit enter
    * Project Setup > select the project using your arrow keys, hit the space bar and hit enter
    * What do you want to use as your public directory? (public) > type `public` and hit enter
    * Configure as a single-page app (rewrite all urls to /index.html)? (y/N) > type `n` and hit enter
4. run `firebase deploy`

### After changes are made
Each time you are ready to re-deploy run `firebase deploy`


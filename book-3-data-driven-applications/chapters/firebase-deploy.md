# Deploying Your Project With Firebase

1.  Globally install the Firebase tools on your machine (1x per machine)

`npm install firebase-tools -g`

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
    * Select `hosting` using your arrow keys, hit the space bar and hit enter
    * Project Setup > select the project using your arrow keys, hit the space bar and hit enter
    * What do you want to use as your public directory? (public) > type `build` and hit enter
    * Configure as a single-page app (rewrite all urls to /index.html)? (y/N) > type `y` and hit enter
    * IF it asks you if you want to overwrite > type `n` and hit enter
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


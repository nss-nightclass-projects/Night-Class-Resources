# How to do Authentication for a React SPA (NO ROUTES)

## Topics Covered / Functionality Implemented
- Google Auth Login button. Nav bar with Logout link. 

## Where to put Api Keys
- We are now exporting a simple javascript object from a javascript file that holds our apiKeys information. 
  - This file should be added as a new line to your .gitignore file: `/src/helpers/apiKeys.js`.
  - You should make an `apiKeys.js.example` file that will not be ignored.
  
## Firebase Intialization
- In our App component, within the componentDidMount lifecycle method, we are going to have our firebase intialization trigger. 
```javascript
const firebaseApp = () => {
  // check if firebase app exists.  If not create one.
  if (!firebase.apps.length) {
    firebase.initializeApp(constants.firebaseConfig);
  }
};
```

# Move files for better organization
`create-react-app` throws all the files at the root of src.  Thats nice until you have components and then its gets real crowded fast.  Lets fix that.

### Create App Folder
All the App stuff should be in a folder together
1. Create `src/App` and move `App.js` and `App.scss` into there.
2. Rename `App.js` to `index.js`
3. Delete `logo.svg`
4. In `App/index.js` remove logo import statement and image tag

### File Structure
Your file structure should now look like this:

<img width="230" alt="Screen Shot 2021-04-03 at 6 06 30 PM" src="https://user-images.githubusercontent.com/29741570/113493689-5e735c80-94a7-11eb-8514-e7138bd6885b.png">

[Return to Instructions](../react-setup.md)

Or, on to the next part:

[Add eslint](https://github.com/nss-nightclass-projects/Night-Class-Resources/blob/master/book-4-react/chapters/react-setup-steps/add-eslint.md)

# Remove testing
`create-react-app` comes with the jest testing framework already installed.  This is awesome!

Spoiler alert - we won't have time to explore this with the little class we have left so we are going to remove the testing (you can always add it back later if you want).

Do the following:
1. Delete `src/App.test.js`
2. Delete `src/setupTests.js`
3. Go to the package.json file and remove this line from the scripts section:
```json
"test": "react-scripts test",
```
## Edit title
1. go to `public/index.html` and change the title tag

## Modify .gitignore
Add the following to the top of the .gitignore file
```js
.vscode/
package-lock.json
dist/
.firebase/
```

[Return to Instructions](../react-setup.md)

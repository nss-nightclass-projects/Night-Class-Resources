# Frontend Dependencies
Up until this point we have always accessed front end libraries via CDN links.  This has some pros and cons.  Now that we are using webpack there is no reason for us not to use webpack to build those assets for us.  We already have webpack bundling our js file so we can easily use NPM to install things like bootstrap and then use webpack to bring those libraries into our projects.

## Installing Regular Dependencies
When we use frontend libraries we need to install them as dependencies NOT dev dependencies.  These libraries are REQUIRED in order to run the project.  We can install some common frontend libraries like this:

```sh
npm install axios bootstrap jquery popper.js --save
```
You should now see these four packages under the dependencies object in the package.json file.  Our package.json file knows to save this stuff as regular dependencies because of the `--save` flag at the end of the line.

We can then use regular import statements to start using these libraries in our projects.  Look below to see how we can import bootstrap into our code and start using it.

### Bootstrap
When using bootstrap we need to include 2 things - the js and the css.  To do this we need two different import statements.

For the CSS we will import the scss version of bootstrap into our main.scss file.  That import statement should be at the top of the file link this:
```
@import "~bootstrap/scss/bootstrap";
```

For the JS we can import the node_module into main.js with the following code:
```js
import 'bootstrap';
```
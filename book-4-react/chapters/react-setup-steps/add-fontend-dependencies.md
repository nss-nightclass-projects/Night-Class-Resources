# Add Front End Dependencies
Just like with modules there are certain front end dependencies we will want to install and use.

```shell
npm install axios bootstrap firebase reactstrap @fortawesome/fontawesome-free prop-types --save

```
### Bootstrap
Bootstrap and react are a little special together.  We installed bootstrap so we can use the css file.  If you need the javascript portions of bootstrap (like modals or carousels) install a package called reactstrap.

Import Bootstrap CSS in the `src/index.js` file:
```js
import 'bootstrap/dist/css/bootstrap.min.css';
```
Bootstrap should now be ready to go - you can test by adding a button in App.js

### Fontawesome
Add the following line to the top of the index.scss file:
```scss
@import "~@fortawesome/fontawesome-free/css/all.min.css";
```
Fontawesome should now be ready to go - you can test by adding your favorite icon in App.js


### All the others
Axios and firebase should be good to go like usual - just import them where you need them.


[Return to Instructions](../react-setup.md)

Or, on to the next part:

[Update `App/index.js`](https://github.com/nss-nightclass-projects/Night-Class-Resources/blob/master/book-4-react/chapters/react-setup-steps/react-classes.md)

# Task Runners

## Why use task runners?
* Using a task runner allows you to add automation to your application
* Things we want to happen automatically:
  * Check our code for errors
  * Bundle all our JS files into 1 file (to rule them all)
  * Convert SCSS into CSC
  * Minify/Uglify our JS and CSS
  * Copy files to a location for deployment

## Popular Task Runners
### Broccoli
[Broccoli](https://github.com/broccolijs/broccoli) Is a fast plugin based pipeline based on the Ruby on Rails asset pipeline but build on node.  It is very flexable but does not currently have a large support base.

### Gulp
[Gulp](https://gulpjs.com/) treats your code like a list of files that requries a series of operations to be applied.  It can be difficult to configure.

### Grunt
[Grunt](https://gruntjs.com/) is a plugin based task runner.  Once a plugin is installed very little configuration is required.  Until recently it has been the most popular task runner.

### Webpack
[Webpack](https://webpack.js.org/) currently the most popular JS task runner.  It is magical and amazing but can also be hard to configure.  Webpack was built first as a module bundler and since then has expanded to do a lot of the task runner stuff.  Because of this it has a lot more out of the box than some of the other task runners.

## Getting Webpack Started

### Installs
We will be installing everything using npm (remember that one time we used npm to install http-server?  it was like day 2 of class...).  To see exact instructions for how we are going to do installs for webpack, scss, ES6 modules, js linting click [HERE](./webpack-installs.md).

### Configuring Webpack
To see instructions for how we are going to configure webpack to DO ALL THE THINGS click [HERE](./webpack-configure.md).

### Configuring ESLint

To see instructions for how we are going to configure eslint and webpack click [HERE](./webpack-eslint.md).

### Configuring Front End Dependencies
To see instructions for how we are going to run bootstrap and jquery with webpack click [HERE](./webpack-frontend-dependencies.md).

### Run Webpack
Now that we have everything setup we can start running webpack.  Click [HERE](./webpack-run.md) to see how.

#### Some extra stuff
* [Adding images](./webpack-images.md) - how to add images from an images folder when you are using a webpack project
* [Axios](./axios.md) - the new and improved XMLHttpRequest.
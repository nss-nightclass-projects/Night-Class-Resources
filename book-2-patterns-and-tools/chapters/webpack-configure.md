# Configuring Webpack

## webpack.config.js
Once webpack is installed via npm packages all the configuration you need for it will go in a webpack.config.js file at the root.

This file should look like this:
```js
const webpack = require('webpack');
const HtmlWebPackPlugin = require("html-webpack-plugin");
const MiniCssExtractPlugin = require("mini-css-extract-plugin");
module.exports = {
  entry: './src/javascripts/main.js',
  devtool: "eval-source-map",
  module: {
    rules: [
      {
        enforce: "pre",
        test: /\.js$/,
        exclude: /node_modules/,
        loader: "eslint-loader",
	options: {
          formatter: require('eslint/lib/cli-engine/formatters/stylish')
        }
      },
      {
        test: /\.js$/,
        exclude: /node_modules/,
        use: {
          loader: "babel-loader"
        }
      },
      {
        test: /\.html$/,
        use: [
          {
            loader: "html-loader",
            options: { minimize: true }
          }
        ]
      },
      {
        test: /\.scss$/,
        use: [
          MiniCssExtractPlugin.loader,
            { loader: 'css-loader', options: { sourceMap: true, importLoaders: 1 } },
            { loader: 'sass-loader', options: { sourceMap: true } },
        ],
      },
      {
        test: /\.(png|svg|jpg|gif)$/,
        use: ['file-loader']
      },
      {
        test: /\.(woff|woff2|eot|ttf|otf)$/,
        use: ['file-loader']
      }
    ]
  },
  plugins: [
    new HtmlWebPackPlugin({
      template: "./src/index.html",
      filename: "./index.html"
    }),
    new MiniCssExtractPlugin({
      filename: "[name].css",
      chunkFilename: "[id].css"
    }),
    new webpack.ProvidePlugin({
      $: "jquery",
      jQuery: "jquery"
    }),
    new webpack.DefinePlugin( {
      'process.env': JSON.stringify(process.env || dotenv.parsed),
    }),
  ],
  output: {
    path: __dirname + "/build",
    filename: "bundle.js"
  }
};
```

Lets go over each section of this file.
### Imports
Just like with our modules anything we need to import goes at the top of the file.  You will see that instead of import statements we are using `require`.  `require` and import do very similar things. `require` is generally used by things that are node.js based.  Import is generally used when using ES6 and behind the scenes when chrome/babel process the ES6 to ES5 they convert the `import` into a `require`.

The two libraries we are importing are `html-webpack-plugin` and `mini-css-extract-plugin`.  These two libraries are not required for webpack to do its thing but they are needed for the configuration we have.  So think of these imports as optional enhancements for webpack.

`html-webpack-plugin` is a plugin that is used to create html files.  This way we can have a template index.html file that includes any divs we need and then we let this plugin all in all the script and link tags our project needs.

`mini-css-extract-plugin` is a css extraction plugin.  We will be importing our SCSS into our javascript files (OMG crazy). This plugin searches through the javascript build and extracts out all the SCSS to create a css file that can then be linked to our index.html.

`webpack` is exactly what it sounds like - the webpack library.  We are including it in order to add plugins to our build process.

### Entry
The entry key is used to tell webpack where your entry point file is located.  Webpack by default has an entry point of `src/index.js`  but we are used to having an entry point of `main.js`.  So we can add the optional entry key to specify our own entry point.  We will sent the value of entry to the following path: `./src/javascripts/main.js`.

### Module
The module section of this file allows us to create a bunch of tasks for webpack to complete.  We do this by creating each task as an object and putting all the tasks in an array thats called rules.  Lets go through each of these tasks.

#### Eslint
```js
{
  enforce: "pre",
  test: /\.js$/,
  exclude: /node_modules/,
  loader: "eslint-loader"
}
```
This task happens before all other tasks run.  In this task we tell webpack to run eslint on ALL files with an extension `.js` that are not in the `node_modules` folder.  If this task comes back with any errors it fail the build process and none of the other tasks will run.  This means your code must be ERROR FREE in order for it to work.

#### Babel (ES6 to ES5)
```js
{
  test: /\.js$/,
  exclude: /node_modules/,
  use: {
    loader: "babel-loader"
  }
}
```
This task uses the `babel-loader` package to convert all of our ES6+ code into ES5 so old browsers (Internet Explorer) can run our code.  It converts any files that end in `.js` that are not in the node_modules folder.

#### HTML Bundling
```js
{
  test: /\.html$/,
  use: [
    {
      loader: "html-loader",
      options: { minimize: true }
    }
  ]
}
```
This task uses the `html-loader` package to copy over all of your html files to the `build` folder. It copies any files that end in `.html`.

#### SCSS to CSS
```js
{
  test: /\.scss$/,
  use: [
    MiniCssExtractPlugin.loader,
      { loader: 'css-loader', options: { sourceMap: true, importLoaders: 1 } },
      { loader: 'sass-loader', options: { sourceMap: true } },
  ],
}
```
This task uses the `sass-loader` package to convert any files that end in `.scss` to css.  Then it uses the `css-loader` package via the `MiniCssExtractPlugin` plugin to copy those css files over to the `build` folder.

#### Images
```js
{
  test: /\.(png|svg|jpg|gif)$/,
  use: ['file-loader']
}
```
This task uses the `file-loader` package to look for any image files (files that end in png, svg, jpg, or gif) and copies them over to the `build` folder.

#### Fonts
```js
{
  test: /\.(woff|woff2|eot|ttf|otf)$/,
  use: ['file-loader']
}
```
This task uses the `file-loader` package to look for any font files (files that end in woff, woff2, eot, ttf, or otf) and copies them over to the `build` folder.

### Plugins
The plugins section is where we configure third party plugins.  In our case we are configuring the four packages we are requiring into this file.

For the `html-webpack-plugin` package we need to give it the location of our `index.html` file and tell it what we want that file to be called when webpack builds this project (also `index.html`).

For the `mini-css-extract-plugin` package we need to tell it what to name the output files.  In this case we are use variable substitution `[name].css`.  This tells the plugin to name the file the same thing in the output it was named in the input.  So a file we write called `main.scss` will be converted from scss to css and then written as `main.css` in the `build` folder.

For the next two plugins we are using `webpack`:
- We would like to include `jquery` into our default build.  This way we can use jquery selectors and functions ANYWHERE without having to inport jquery into every file.  Using `webpack.ProvidePlugin` allows us to directly import jquery into our main project so `$` is available everywhere.
- We would like to ensure that our API keys and enviorment variables are secure and acessible in our code, so we are using the `DefinePlugin` to tell our installation where to find the vars in both dev and prod environments.

### Output
The output section tells webpack where to put code that it processes and what to call it.  In our configuration we tell webpack to make a folder called `build` at the root of our project and to call the minified javascript file `bundle.js`;

### Exporting
You will notice that all the above sections (entry, module, plugins, and output) are key/value pairs inside an object.  That object has a `module.exports` in front of it.  You can think of `module.exports` as the node.js equivalent of `export default {}`.  Webpack is looking for an object to be exported from the `webpack.config.js` file.  Whatever object it finds it uses for configuration.

# Creating a Project Using Webpack, Linters, Image Bundling and Now With !!🎉🎉AXIOS🎉🎉!!

## Setup
1. **GitHub.com** [Create a new repo on GitHub](https://github.com/new)
1. **GitHub.com** Select the default options
1. **Local Command Prompt** Create a new directory in the appropriate place
1. **Local Command Prompt** CD into the new directory
1. **Local Command Prompt** Complete the default steps given by GitHub
1. **Local Command Prompt** `mkdir src`
1. **Local Command Prompt** `cd src && touch index.html index.js index.scss && cd ..`
1. **Local Command Prompt** `touch .eslintignore .eslintrc .gitignore webpack.config.js`
1. **Local Command Prompt** `npm init --y`

### Content:

#### .eslintignore
```
webpack.config.js
node_modules
```

#### .eslintrc
```json
{
  "parserOptions": {
    "ecmaVersion": 6,
    "sourceType": "module"
  },
  "extends": "airbnb-base",
  "globals": {
    "document": true,
    "window": true,
    "$": true,
    "allowTemplateLiterals": true
  },
  "rules": {
    "no-console": 1
  }
}
```

#### .gitignore
```
node_modules/
dist/
```

#### package.json (These should be ADDED to your package.json, not overwriting the whole file)
```json
{
  "scripts": {
    "build": "NODE_ENV=production webpack",
    "lint": "eslint ./src --ext .js --fix",
    "dev": "NODE_ENV=development webpack-dev-server --content-base dist --hot",
    "start": "npm run lint && npm run dev"
  },
  "devDependencies": {
    "babel-core": "^6.26.0",
    "babel-loader": "^7.1.2",
    "babel-preset-env": "^1.6.1",
    "css-loader": "^0.28.9",
    "eslint": "^5.8.0",
    "eslint-config-airbnb-base": "^13.1.0",
    "eslint-loader": "^2.1.1",
    "eslint-plugin-import": "^2.14.0",
    "extract-text-webpack-plugin": "^3.0.2",
    "file-loader": "^2.0.0",
    "html-webpack-plugin": "^2.30.1",
    "node-sass": "^4.7.2",
    "sass-loader": "^6.0.6",
    "style-loader": "^0.20.2",
    "url-loader": "^1.1.2",
    "webpack": "^3.11.0",
    "webpack-dev-server": "^2.11.1"
  },
  "dependencies": {
    "axios": "^0.18.0",
    "bootstrap": "^4.1.3",
    "jquery": "^3.3.1",
    "popper.js": "^1.14.4"
  }
}
```

#### webpack.config.js
```js
const path = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');
const ExtractTextPlugin = require('extract-text-webpack-plugin');

const env = process.env.NODE_ENV || 'development';
const isDev = env === 'development';
const isProd = env === 'production';

const extractScss = new ExtractTextPlugin({
  filename: 'index.css',
  disable: isDev
});

module.exports = {
  entry: {
    bundle: './src/index.js'
  },
  output: {
    path: path.resolve(__dirname, 'dist'),
    filename: 'bundle.js'
  },
  plugins: [
    new HtmlWebpackPlugin({
      template: path.resolve(__dirname, 'src/index.html')
    }),
    extractScss
  ],
  module: {
    rules: [{
      enforce: 'pre',
      test: /\.js$/,
      exclude: /node_modules/,
      use: 'eslint-loader'
    }, 
    {
      test: /\.(png|jp(e*)g|svg)$/,  
      use: [{
          loader: 'url-loader',
          options: { 
              limit: 8000, // Convert images < 8kb to base64 strings
              name: 'images/[hash]-[name].[ext]'
          } 
      }]
    },
    {
      test: /\.js$/,
      exclude: /node_modules/,
      use: 'babel-loader'
    }, {
      test: /(\.css|\.scss)$/,
      exclude: /node_modules/,
      use: extractScss.extract({
        use:[
          {loader: 'css-loader'},
          {loader: 'sass-loader'}
        ],
        fallback: 'style-loader'
      })
    }]
  },
  devServer: {
    historyApiFallback: true,
    open: isDev ? true : false
  }
};
```

#### src/index.scss
```
@import "~bootstrap/scss/bootstrap";
```

#### src/index.js
```js
import $ from 'jquery';
import 'bootstrap';
```

## Setup cont'd
1. **Local Command Prompt** `npm install`
1. **Local Command Prompt (VS Code)** `npm start`

___

## Using Axios
> For every file you will need to make an XHR request in, you will need to require Axios
```js
import axios from 'axios';

const examplePromise = () => new Promise((resolve, reject) => {
  axios.get('http://localhost:3001/example')
    .done((data) => {
      resolve(data);
    })
    .fail((error) => {
      reject(error);
    });
});
```

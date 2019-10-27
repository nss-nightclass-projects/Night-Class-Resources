# Eslint
Eslint is a linting tool for javascript. Code linters are great tools because they often help you catch errors before your code runs.  They also help keep code bases consistent.  If everyone on a development team is following a certain set of rules about how their code should look then at the end of the day there will be a lot of consistency with how the code looks.

## VS Code
Want to be able to "see" your errors as you actually type them before webpack yells at you?  There is a sweet vs code extension out there called eslint.  Find it [HERE](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint).


## Setup Files
To use eslint we will need two different configuration files.

### .eslintignore
The `.eslintignore` file operates very similarly to the `.gitignore` file.  Anything that is in the `.eslintignore` file will be ignored from linting.  Currently you should have the following entries in your `.eslintignore`.
```js
webpack.config.js
node_modules
```

### .eslintrc
The `.eslintrc` file is where we configure our rules for eslint.  Your file should look like this:
```js
{
  "parserOptions": {
    "ecmaVersion": 9,
    "sourceType": "module"
  },
  "extends": "airbnb-base",
  "globals": {
    "document": true,
    "window": true,
    "$": true,
    "XMLHttpRequest": true,
    "allowTemplateLiterals": true
  },
  "rules": {
    "no-console": [1, { "allow": ["error"] }],
    "no-debugger": 1,
    "class-methods-use-this": 0,
    "linebreak-style": 0,
    "max-len": [1,200,2]
  }
}
```

Lets break down what is happening here.
#### parserOptions
In this section you define how your code is written.  Here we are telling eslint that we are using ES6 and that we are writing modular code.

#### extends
The extends section is where we can use existing configurations.  In our case we are going to use the linting guide that airbnb created.  We used npm to install `eslint-config-airbnb-base` so by adding `airbnb-base` into the extends section eslint knows to pull that node_module.

#### globals
This section is for any global variables that you want to use that eslint may think are undefined.  Things like `window` or `document`.  We are also saying that our code will be using template literals.

#### rules
This is the section that you can add rules for eslint to check.  In our case since we are using the airbnb linting guide the rules section will be the place we are over-riding styles.  In our case there are 4 things we need to over-ride.
* **no-console** - the airbnb guide does not allow any version of `console`  to catch errors we would like to be able to use `console.error`.  The line above allows `console.error` but no other consoles.
* **no-debugger** - airbnb does not allow any debugger statements AT ALL.  Sometimes they can be useful to instead of failing on a debugger we will throw a warning.  This will remind you to delete them before you push code but still use them as you develop.
* **class-methods-use-this** - this rule doesn't matter for now.  It is in here for when we start react.
* **linebreak-style** - this rule is in here for windows users.  Windows and mac machines add different characters for line breaks.  This causes problems with git and eslint.  So we are ignoring linting on line breaking.

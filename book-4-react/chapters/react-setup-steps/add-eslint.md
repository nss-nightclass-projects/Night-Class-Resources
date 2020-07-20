# Add eslint

## Installation

1. Install VS Code plugin - [eslint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) (you should already have this)
2. Install airbnb styles
`npm install eslint-config-airbnb-base --save-dev`

## Configuration
Create the `.eslintrc` file at the root of your project like usual and add the following:
```
{
  "parserOptions": {
    "ecmaVersion": 9,
    "sourceType": "module"
  },
  "extends": ["airbnb-base", "react-app"],
  "globals": {
    "document": true,
    "window": true,
    "$": true,
    "XMLHttpRequest": true,
    "allowTemplateLiterals": true
  },
  "rules": {
    "no-console": [1, { "allow": ["error", "warn"] }],
    "no-debugger": 1,
    "class-methods-use-this": 0,
    "linebreak-style": 0,
    "max-len": [1,200,2]
  }
}
```

## Test it out
Your project should now be running eslint.

To test that it is working go into index.js and change one of the import statements to have double quotes instead of single - this should throw the strings must use single quotes error.

If you are getting any other errors in the project ignore them for now.

There is one major difference between how we use eslint now and how we did before.  Now it serves as a tool - it will **NOT** fail your build if you have errors.  With the VS Code plugin you should see files with errors in red.  Do yourself a favor - fix the errors before you move on.  It will make your code cleaner and probably catch errors like misspelled words etc.


[Return to Instructions](../react-setup.md)

Or, on to the next part:

[Add Front End Deps](https://github.com/nss-nightclass-projects/Night-Class-Resources/blob/master/book-4-react/chapters/react-setup-steps/add-fontend-dependencies.md)

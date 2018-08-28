# Chrome Dev Tools

Dev tools super-charge your ability to customize your web applications and investigate how your code is working. You should **always** have your dev tools open.

You will use some dev tool panels  more than others. The red boxes will be most used in this class.
![Dev Tools Top Level](../images/dev-tools-panels.png)


## Three Ways to Open
1. Shortcut Keys:
    - Mac: CMD + OPT+ I
    - Windows: CTRL + SHIFT + I
1. Right Click
    - Right click on the screen and select inspect. Takes you to that HTML element.
1. Menu
    - Chrome Menu > More Tools > Developer Tools

## Your Most Important Panels

### Elements Panel
- Inspect and live-edit the HTML and CSS on the page
  - See the full dom tree and navigate it one element at a time
  - View ALL CSS rules applied to a specific element
  - See what CSS rules have been overridden
  - Modify CSS rules in real time

### Console Panel
- Fast JS Playground, console holder, test values
  - JS in the browser - type in any JS and watch it go
  - Any console.logs you put in print here
  - When you have stopped your code execution (see [Debugging](#debugging)), you can print out the values of your javascript variables here.

### Sources Panel
- Where the pros debug their code.
  - Allows you to open any JS/CSS file and see the code in it
  - You can place breakpoints so you don’t need to put in debuggers/console.logs
  - At each breakpoint you can see what variables are in your DOM

### Network Panel
- Shows you the status of all assets you try and load into the site
  - Shows all assets that were requested
  - Gives you load times on each resource
  - Gives you status of each source

### Application Panel
- Where the cookies live
  - View and edit things in local/session storage
  - View and edit cookies
  - View and edit Application Cache

## <a name="debugging"></a>Debugging Your Code in the Browser

There are three main methods for debugging code your code in the browser.
1. `console.log`
1. `debugger;`
1. Breakpoints

### console.log

The `console.log()` method in JavaScript allows you to display any information you want in the Console tab of the browser. You can display simple messages.

### debugger

The `debugger;` keyword stops the execution of your javascript code - it allows you to review your JS code and see what the values of variable are at that moment. In the example below, I put in a `debugger` statement so that I can see what is contained inside the colors array, and then I can step one line of code at a time and see how it changes.

![Debugger Gif](../images/debugger-statement.gif)

### Breakpoints

In this example, I have a block of code that responds to user input, so it doesn't actually execute as soon as the page loads. I put a breakpoint on the line of code that I want to examine, and when the user performs the appropriate action, my JavaScript halts execution and I can examine the code.

## Additional Resources
- Read the Chrome Dev Tools [Documentation](https://developers.google.com/web/tools/chrome-devtools/)
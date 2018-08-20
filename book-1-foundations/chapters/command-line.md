# Command Line Basics

## Introduction
The command line is a text based interface that allows you to control your computer.  You can use it to navigate your machines file structure and perform commands that you can't using just your computers file explorer.

## Tools
* __Mac Users__:  You will be using an application called [Terminal](https://support.apple.com/guide/terminal/welcome/mac).  If you want another option that has some slightly flashier looking display take a look at [iTerm2](https://www.iterm2.com/)
* __Windows Users__:  You will be using [Git Bash](https://git-scm.com/book/en/v2/Getting-Started-The-Command-Line) for 99.9% of the things we need.  We will let you know when specific commands require you to use something else.

## Why you need to know it
* __Control:__ Edit permissions, see hidden files, execute powerful commands (example:  running a project as an administrator)
* __Package Control:__ Install and interact with applications that have no other user interface (example: installing http-server)
* __Tasks Runners:__ Various processors that will aid in development (example: grunt, gulp, broccoli, or webpack)
* __Server control:__ Create scripts that control other machines (example: writing a script that deploys your code or getting logs from another server)

You will be using the command line EVERY day in this class.

## Rule #1 of Command Line:
__Always know where you are__ `pwd`

## Common Commands (Unix Based)
For all these commands `>` indicates a code block and `#` indicates a comment.  To run each command type everything after the `>` but before the `#`.
1. Print Working Directory - print working directory; show where you are.

    ```>  pwd```

2. Change Directory - use this to change what folder you are in

    ```>  cd .. #this goes back one directory```

    ```>  cd ~ #this goes back to the root of your machine```

    ```>  cd ../cookies #this goes back one directory and then into a folder called cookies```

3. Make a New Directory - creates a new folder

    ```>  mkdir bananas #this makes a folder called bananas in whatever location you are currently in```

4. Create a new file - create a new file

    ```>  touch index.html #this makes a files named index.html in your current location```

5. list directory - lists all the files/folders in the directory you are currently in

    ```>  ls #lists current files/folders```

    ```>  ls -a #lists current files included hidden files/folders```

    ```>  ls -al #lists current files included hidden files/folders the long way```

6. Move a file/filter - this moves things where you want them

    ```>  mv index.html bananas/index.html #move index.html into the bananas folder```

7. Copy a file or directory

    ```>  cp index.html ./cat.html  #make a copy of index.html and call it cat.html in this same folder```

8. Deleting files/folders - delete file/folder this can't be undone

    ```> rm cat.html  # removes the cat.html file```
    ```> rm -rf cookies  # removes the cookies folder and everything inside it```

    :exclamation: WARNING: :exclamation:

    This command will delete your ENTIRE computer DON'T RUN IT

    ```> rm -rf *```


9. Open stuff in finder window - see things in the finder window

    Mac: ```>  open . # opens current folder in Finder window```

    Windows: ```>  explorer . # opens current folder in Finder window```

10. Learn more about command line via command line - open terminal help

    Mac: ```>  man mv # opens terminal manual about mv command```

    Windows: ```> mv --help # opens terminal manual about mv command```

11. Open stuff in VS Code

    ```>  code . #opens the current directory in VS code.```

## VIM
If you see this don't panic:
![VIM](../images/vim.png)
We will talk more about this in a few weeks but for now follow these steps:
* hit escape
* type `:wq`
* hit enter

## Class File Structure
For the next six months we will be working through three different milestones.  In order to make that go smoothly lets create a file structure so we are all coding in the same place.  Use the command line commands you just learned to create the following file structure:
![workspace file structure](../images/workspace_file_structure.png)

## Mini Challenge
Move the directory `html-css-101` you created in your HTML and CSS lesson and all of its contents from the `Desktop` into the directory `~/workspace/foundations/inclass`
# Computer Setup

## Hardware

Up until now, you didn't have the power to destroy your machine, but within the first two weeks of attending Nashville Software School you will have that power. Go buy a backup drive RIGHT NOW and start backing up your entire hard drive.

**Seriously, right now!**

## Online Services

### Github

Github is the primary site that software developers throughout the world use to store their code, and share it with other developers. Visit the [sign up page](https://github.com/join) and create your own, free account.


## Installs for Mac - OSX
### Xcode Command Line Tools

Since you are going to be learning how to be a professional software developer, you will be using your computer terminal heavily. OSX users need to install some baseline tools to use more advanced things later in the course.

Type this command into your terminal, and then wait a while.

```sh
xcode-select --install
```

### Homebrew

Visit the [homebrew home page](http://brew.sh/) and follow the single instruction there to get it installed.  This is a package manager for OSX.  It makes installing cool stuff easy.

### Node

Node is basically server side JavaScript.  We will be using it to serve up web pages and installing js libararies.  We will use brew to install it:

```sh
brew install node
```

### HTTP-Server
Http-server is a node plugin that allows us to run web pages.  We will install it using node's NPM (Node Package Manager) service.
```sh
npm install -g http-server
```

### VS Code
This is the GREATEST TEXT EDITOR OF ALL TIME.  All other text editors are sad in comparrison.  We will install it using brew
```sh
brew cask install visual-studio-code
```

## Installs for Windows
### Install Git Bash

Visit the [Git powershell](http://www.git-scm.com/downloads) download page click the "Download for Windows" button, and once complete, install the software. Powershell is a command line utility that allows you to run most Unix command inside a Windows environment. This will help you have the same vernacular as the rest of the class, since having a *nix environment is preferred and is how the class is taught.

### Node
Node is basically server side JavaScript.  We will be using it to serve up web pages and installing js libararies.  To install visit the node [website](https://nodejs.org/) and click on the green button with the version that says LTS next to it.

### HTTP-Server
Http-server is a node plugin that allows us to run web pages.  We will install it using node's NPM (Node Package Manager) service.
```sh
npm install -g http-server
```

### VS Code
This is the GREATEST TEXT EDITOR OF ALL TIME.  All other text editors are sad in comparrison.  We will install it via the VS Code [Website](https://code.visualstudio.com/)


## Installs For Everyone
### Install Slack

Do not use the browser-based interface for Slack. [Download](https://slack.com/downloads/) and use the client. Let us know if you did not get an invitation to the Nashville Software School Slack organization, and we'll send you one immediately.

### Google Chrome

[Google Chrome](https://www.google.com/chrome/browser/desktop/index.html) is the most popular browser for web developers because of the powerful tools it provides to test code, manipulate documents, and measure performance.

### Create SSH key

SSH is a technology that allows you to create a very secure connection between your computer, and a computer located somewhere else in the world. It's an acronym for Secure SHell. When you create an SSH key on your computer, it actually creates two files

1. A public key file that you share with other people and computers. It is usually named `id_rsa.pub`.
1. A private key file that you never, ever, ever, ever, ever share with anyone. It is usually named `id_rsa`.

Step 1:  Follow the Github instructions for [MAC](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/#platform-mac) or [PC](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/#platform-windows) for creating a new SSH key, and providing your public key to Github, so that you can establish a secure connection between your computer and Github's computers.

Step 2: Add the SSH key to your [github account](https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/)

Step 3: Check your github key using your terminal.
```sh
ssh -T git@github.com
```
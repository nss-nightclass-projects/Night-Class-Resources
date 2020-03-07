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

Node is basically server side JavaScript.  We will be using it to serve up web pages and installing js libraries.  We will use brew to install it:

```sh
brew install node
```

### HTTP-Server
Http-server is a node plugin that allows us to run web pages.  We will install it using node's NPM (Node Package Manager) service.
```sh
npm install -g http-server@0.8.0
```

### VS Code
This is the GREATEST TEXT EDITOR OF ALL TIME.  All other text editors are sad in comparison.  We will install it using brew
```sh
brew cask install visual-studio-code
```

## Installs for Windows
### Install the Windows Subsystem for Linux

You'll need to install and enable the Windows Subsystem for Linux by:
1. Go to the `Start` menu (windows key) and search for `PowerShell`.
2. Run PowerShell as an Administrator. To do this, find the PowerShell application, then right-click on it and choose "Open as adminsitrator".
3. Copy and paste this command into your PowerShell:

        Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux

4. Restart your computer when prompted to

Once you've completed the above steps **and** restarted your computer, you will install Ubuntu in the Microsoft Store [here](https://www.microsoft.com/en-us/p/ubuntu/9nblggh4msv6?activetab=pivot:overviewtab). We'll use this in the next step: Installing the Windows Terminal.

### Install Windows Terminal

Later in the instructions, we will ask you to type a command into your terminal. For Windows, this is the **Windows Terminal (Preview)** application using **Ubunutu**.

Visit the [Windows Terminal (Preview)](https://www.microsoft.com/en-us/p/windows-terminal-preview/9n0dx20hk701?activetab=pivot:overviewtab) download page and open it in the Microsoft Store App. This will be your default terminal (using Ubuntu) which you will use to navigate your file system, and run development tools throughout the course.

Once Windows Terminal is installed:
1. Go to the `Start` menu (windows key) and search for `Windows Terminal`
2. Open `Windows Terminal (Preview)`
3. This will open up a new PowerShell Tab by default. In the top left corner of the terminal click the `Down Arrow`, and select **Ubuntu** to open a new Ubuntu Tab.

    > Ubuntu will begin to install and you'll be asked to wait for a minute or two for the installation to complete.

4. Once Ubuntu is done installing, you'll be prompted to create a new user (and its password).

### Node

You will install Node.js using the Windows Terminal. Open Windows Terminal, and in a **new Ubuntu Tab**, copy and paste the following lines:
```
curl -sL https://deb.nodesource.com/setup_13.x | sudo -E bash -
sudo apt-get install -y nodejs
```
After a while, you will be prompted with a message asking for permissions. Using the arrow keys on your keyboard, select **Yes** and hit the enter key to continue installing Node.js.

### HTTP-Server
Http-server is a node plugin that allows us to run web pages.  We will install it using node's NPM (Node Package Manager) service.
```sh
npm install -g http-server
```

### VS Code
This is the GREATEST TEXT EDITOR OF ALL TIME.  All other text editors are sad in comparison.  We will install it via the VS Code [Website](https://code.visualstudio.com/)


## Installs For Everyone
### Install Slack

Do not use the browser-based interface for Slack. [Download](https://slack.com/downloads/) and use the client. Let us know if you did not get an invitation to the Nashville Software School Slack organization, and we'll send you one immediately.

### Google Chrome

[Google Chrome](https://www.google.com/chrome/browser/desktop/index.html) is the most popular browser for web developers because of the powerful tools it provides to test code, manipulate documents, and measure performance.

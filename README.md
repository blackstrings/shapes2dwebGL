# UW Stout CS 343 2D Project Base
#### A codebase for building the projects assigned in CS 343, Mathematical Foundations of Computer Graphics, at the University of Wisconsin Stout.

## Features
- ESLINT with JavaScript Standard Style configuration
- Latest generation of JavaScript "transpiled" to browser JS (ES5) (via [Babel](https://babeljs.io))
- Browsers synchronize and hot-reload as you make changes (via [Browsersync](https://browsersync.io))
- Module JavaScript that is re-targeted to a web browser env (via [webpack](https://webpack.js.org))
- Packaging and loading of Bootstrap, jQuery, & nanoGL (via [webpack](https://webpack.js.org))
- Pre-configured 'deploy' target to minify and uglify your JavaScript

# Setup
The basic steps for utilizing this repository:

## 1. Clone the repo and pick a Tag:

*Note: As an alternative to cloning the repo, you can just grab the source code for a particular tag by visiting the [releases page](https://github.com/UWStout/gfx-2d-base-vsc/releases) on github.*

---

Navigate into your workspace directory and clone the repo with git:

```
git clone https://github.com/UWStout/gfx-2d-base-vsc.git .
```

Switch to the tag that matches the project you want to work on:

```
git pull --tags
git checkout <tagname>
```

See the [github website](https://github.com/UWStout/gfx-2d-base-vsc/tags) for a list of accepted tag names.

## 2. Install node.js and npm:

Download and install the LTS version of node.js with npm available from https://nodejs.org/en/

## 3. Install dependencies:

Navigate to the repo directory (or use the VS Code terminal) and run:

```
npm install
```

If this is not the first time you have run 'npm install' or if you have just switched
tags, it is a good idea to remove the previously installed dependencies first:

```
rm -rf node_modules/
```

Note, yarn is also supported.

# Working on the Code

While working on the project, you should first run the development server.  Change to
the code repo directory (or use the VS Code terminal) and run:

```
npm run dev
```

This will compile the JavaScript files and package them into 'dist/bundle.js'. It will
also run a local web server on port 3000. Lastly, it opens 'localhost:3000' in your
default web browser.

You can open and edit the files in the project base in your favorite text/code editor
(VisualStudio Code is recommended) and the changes will be automatically reflected in the browser.
If you accidentally close the browser or if you want to open it in a different browser
or have multiple versions open at once, just type 'localhost:3000' into the browser
address bar to talk to the local server.

# Keeping the Browser in Sync

A program called browsersync is used to automatically sense the changes you make and
hot-load them into your running browser or automatically reload the browser.  However,
there are some changes that will cause the browser to get out of sync:

* If you have the developer console open in the browser then it may not refresh automatically.  Just refresh manually when this happens.
* If there is an error in your JavaScript that causes the browser to halt it may not automatically refresh until you fix the code and do a manual refresh.
* If you make changes to HTML or CSS code it will NOT automatically refresh, only JS code.
* If the 'dev' server is not running (e.g. you forgot to run 'npm run dev') it will not refresh.

## Build for production/deployment:

When you project is done and you want to build the FINAL version you would give to normal users, you can build the production or deployment versions. First, to build the production version, adjust your 'run' command to be:

```
npm run prod
```

This builds the 'dist/bundle.js' file differently so that its size is minimized and the code is
further optimized. It also sets the global JS variable `__DEV__` to be false.

The prod script will still run the local dev server so you can test to make sure everything still works. Once you are sure, you can then run the deploy script:

```
npm run deploy
```

This is configured identical to the prod script but it does not run the local browsersync server. It is a good idea to clear everything out of the 'dist' folder before you do this.

## Credits
This code base was largely inspired by:

* https://github.com/lean/phaser-es6-webpack

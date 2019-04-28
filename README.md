# Web Project Holy Grail - 2019

# Table of Contents
1. [Summary](#summary)
2. [I know what I'm doing](#i-know-what-im-doing)
3. [I don't know what I'm doing](#i-dont-know-what-im-doing)

## Summary
### The use of this remote repository

This is the starting point I use for any web project that **does not use** a framework *(for example, Angular.js, React.js, Vue.js, etc.)*. It sets you up with [Gulp 4](https://gulpjs.com/), so you can compile [SCSS](https://sass-lang.com/) into CSS. The SCSS is compiled with the [npm package gulp-sass](https://www.npmjs.com/package/gulp-sass) and organized into the [7-1 folder pattern](https://itnext.io/structuring-your-sass-projects-c8d41fa55ed4) for scalability. It also uses the [npm package browser-sync](https://www.npmjs.com/package/browser-sync/v/2.23.6) to make browsers upload automatically while you work directly on the code. browser-sync will read changes in your HTML, CSS and JS. Check this documentation to learn how to also see those changes updating automatically on your mobile (great for checking responsive styling!).

All this setup is done through [NVM (node version manager)](https://github.com/nvm-sh/nvm) to use [Node.js](https://nodejs.org/en/) and [NPM](https://www.npmjs.com/) without requiring the use of `sudo` on the Terminal. That helps avoid permission errors if you are on a macOS operating system.

**NOTE: ALL STEPS IN THIS GUIDE ASSUME YOU ARE ON A MAC**

**NOTE: THIS REMOTE REPOSITORY DOES NOT CONTAIN A `DIST` FOLDER**

**NOTE: THIS REMOTE REPOSITORY HAS ONE HIGH VULNERABILILTY THAT NEEDS TO BE RESOLVED - 28 APRIL 2019** Learn more about this vulnerability [here](https://github.com/sass/node-sass/issues/2625) or by auditing npm in your project folder:
```
npm audit
```

## I know what I'm doing
### How to quickly use this repository if you've used Gulp 4 before on your machine:

1. Open Terminal and move (`cd`) to whatever folder you use to save your projects.

2. Create your project folder (`mkdir "project-name"`) if you haven't created it yet.

3. Move to your project folder (`cd "project-name"`).

4. Clone this repository in your project folder. Notice the `.` at the end of the command. It is important to include it because that will allow you to clone the remote repository files into your project folder without a parent folder. Learn more about how to [Git clone without project folder](https://magp.ie/2017/03/16/git-clone-without-project-folder/).
```
git clone https://github.com/dmillang/gulp-boilerplate.git .
```

5. The repository does not include the heavy `node_modules` folder thanks to the `.gitignore` file it contains. You need it though, so let's download it in your project folder:
```
npm install
```

6. Almost there, now all you need to do is run the following command to make Gulp 4 compile all the SCSS files and active the BrowserSync (which will most probably open on a `localhost:3000` tab):
```
gulp watch
```

7. Done. You'll see the Terminal is busy watching for updates in the code. If you need to do something with the Terminal just stop `gulp watch` by typing the following on the Terminal:
```
cntrl + c
```

8. NOTE: All this Gulp 4 magic is defined on the `gulpfile.js`. Basically it has two `functions` that `.pipe` a set of actions to make our life easier while developing. The first function `function style()` is called inside the second function `function watch()`. That's why we only need to call `gulp watch` on the Terminal to initiate all we need (SCSS compiler and BrowserSync).

## I don't know what I'm doing
### How to set up this repository if you've never used NVM, Node.js, NPM or Gulp 4 before on your machine:

If you know of the existence of Gulp and its virtues, but you've never use it before in your macOS machine, follow this steps to set up a functioning project folder that uses Gulp with SCSS compiler and BrowserSync:

1. Make sure you start from a clean state by deleting past installations of Node.js and NPM. To do so, follow the top rated answers accepted in this stackoverflow question: ["How do I completely uninstall Node.js, and reinstall from beginning (Mac OS X)"](https://stackoverflow.com/questions/11177954/how-do-i-completely-uninstall-node-js-and-reinstall-from-beginning-mac-os-x).

2. Now it's time to install NVM to have Node.js (and by default, NPM) so that we can use Gulp later on. A clear tutorial to install NVM, Node.js and NPM can be found here: ["Installing Node.js Tutorial: Using nvm"](https://nodesource.com/blog/installing-node-js-tutorial-using-nvm-on-mac-os-x-and-ubuntu/).

3. Check on your Terminal (no matter in which folder you are) that you have successfully installed Node and NPM. It should display which version you are using (doesn't need to much the ones below, although if you've followed the tutorials above you should be able to swtich between different versions thanks to your NVM):

* Check you have Node
```
node -v
```
```
v10.15.3
```

* Check you have NPM
```
npm -v
```
```
6.4.1
```

4. Install gulp globally in your machine:
```
npm install --global gulp-cli
```

5. Check Gulp has been installed globally (don't worry if it says `Local version: version unknown` below the CLI version):
```
gulp -v
```
```
CLI version: 2.2.0
```
6. Now that you are set globally, all you need to do is follow the steps on [I know what I'm doing](#i-know-what-im-doing).
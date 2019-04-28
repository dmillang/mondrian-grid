# Web Project Holy Grail - 2019

# Table of Contents
1. [Summary](#Summary)
2. [I know what I'm doing](#I%20know%20what%20I'm%20doing)
3. [I don't know what I'm doing](#I%20don't%20know%20what%20I'm%20doing)

## Summary
### The use of this remote repository

This is the starting point I use for any web project that **does not use** a framework *(for example, Angular.js, React.js, Vue.js, etc.)*. It sets you up with Gulp 4, so you can compile SCSS into CSS. The SCSS is compiled with the npm package gulp-sass and organized into the 7-1 folder pattern for scalability. It also uses the npm package browser-sync to make browsers upload automatically while you work directly on the code. BrowserSync will read changes in your HTML, CSS and JS. Check this documentation to learn how to also see those changes updating automatically on your mobile (great for checking responsive styling!).

All this setup is done through NVM (node version manager) to use Node.js and NPM without requiring the use of `sudo` on the Terminal. That helps avoid permission errors if you are on a macOS operating system.

**NOTE: ALL STEPS IN THIS GUIDE ASSUME YOU ARE ON A MAC**

**NOTE: THIS REMOTE REPOSITORY DOES NOT CONTAIN A `DIST` FOLDER**

**NOTE: THIS REMOTE REPOSITORY HAS ONE HIGH VULNERABILILTY THAT NEEDS TO BE RESOLVED - 28 APRIL 2019**
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
cntl + c
```

8. NOTE: All this Gulp 4 magic is defined on the `gulpfile.js`. Basically it has two `functions` that `.pipe` a set of actions to make our life easier while developing. The first function `function style()` is called inside the second function `function watch()`. That's why we only need to call `gulp watch` on the Terminal to initiate all we need (SCSS compiler and BrowserSync).

## I don't know what I'm doing
### How to set up this repository if you've never used NVM, Node.js, NPM or Gulp 4 before on your machine:
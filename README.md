# Gulp 4 build for projects which using SASS(SCSS)/LESS/Stylus and JS

## Project Description:
Using these files, you can quickly configure the build of your project on Gulp.

## This build includes:
- [gulp-sass](https://www.npmjs.com/package/gulp-sass) - compilation of SASS, SCSS into CSS;
- [Browsersync](https://browsersync.io/docs/gulp) - browser auto-refresh;
- [gulp-autoprefixer](https://www.npmjs.com/package/gulp-autoprefixer) - automatically arranges vendor prefixes in CSS in accordance with the [Can I Use](https://caniuse.com/) service;
- [clean-css](https://www.npmjs.com/package/clean-css) - CSS optimizer;
- [gulp-concat](https://www.npmjs.com/package/gulp-concat) - file concatenation;
- [gulp-sourcemaps](https://www.npmjs.com/package/gulp-sourcemaps) - creating sourcemaps;
- [gulp-uglify](https://www.npmjs.com/package/gulp-uglify) - Minify JavaScript;
- [del](https://www.npmjs.com/package/del) - Delete files and directories using globs;

## Prerequisites
Install [`Node JS`](https://nodejs.org/en/download/)

Install [`Git`](https://www.atlassian.com/git/tutorials/install-git)


## How to use this build?
Open `cmd` on Windows or `Terminal` on Linux/MacOS and follow next steps:
 - install `gulp` globally - `npm install --global gulp-cli`
 - download build - `git clone https://github.com/alexhamenko/gulp-4-sass`
 - go to the project folder - `cd gulp-4-sass`
 - install packages from package.json - `npm i`
 - run `gulp` command to make sure everything is installed correctly
 
## Files structure
>./src  
>>	/css  
>>>		/main.scss  
>>>		/media.scss  
>>	/js  
>>>		/lib.js  
>>>		/main.js  
>./gulpfile.js  
>./package.json  
>./index.html  

###### `main.scss`, `media.scss`, `lib.js` and `main.js` - these files are used for verifying the correct work of the build. To use your own file, add it to the `src/css` or `src/js` folder and edit correct the corresponding lines in the `cssFiles` and `jsFiles` variables from`gulpfile.js`.

## If you want to use LESS or Stylus preprocessors instead of SASS, do the following steps after downloading this project:

#### LESS:
1. Go to the project folder - `cd gulp-4-sass`
2. Run command `npm i`
3. Run command `npm i -SD gulp-less`
4. Run command `npm uninstall gulp-sass -SD`
5. Change extensions of style files from `scss` to `less` in the `src/css` folder
6. Replace SCSS code with LESS code in the style files from `src/css` folder 
7. Edit gulpfile.js:
    - change `const sass = require('gulp-sass');` to `const less = require('gulp-less');`
    - change files extensions from `scss` to `less` in the `const cssFiles`
    - change `.pipe(sass())` to the `.pipe(less())` in the `styles()` function
    - change `gulp.watch('./src/css/**/*.sass', styles);` to the ` gulp.watch('./src/css/**/*.less', styles);` in the `watch()` function
    - delete `gulp.watch('./src/css/**/*.scss', styles);`
 
#### Stylus:
1. Go to the project folder - `cd gulp-4-sass`
2. Run command `npm i`
3. Run command `npm i -SD gulp-stylus`
4. Run command `npm uninstall -SD gulp-sass`
5. Change extensions of style files from `scss` to `styl` in the `src/css` folder
6. Replace SCSS code with Stylus code in the style files from `src/css` folder 
7. Edit gulpfile.js:
    - change `const sass = require('gulp-sass');` to `const stylus = require('gulp-stylus');`
    - change file's extensions from `scss` to `styl` in the `const cssFiles`
    - change `.pipe(sass())` to `.pipe(stylus())` in the `styles()` function
    - change `gulp.watch('./src/css/**/*.sass', styles);` to the ` gulp.watch('./src/css/**/*.styl', styles);` in the `watch()` function
    - delete `gulp.watch('./src/css/**/*.scss', styles);`


Based on [this build](https://github.com/morphIsmail/gulp_settings)

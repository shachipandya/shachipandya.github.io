---
layout: post
title: "Automating Tasks with Gulp.js"
subtitle: "Because not learning new things is lame"
label: "Software"
---

Another article on coding and tinkering with software. I apologise but this new year, I have some resolutions that I have to adhere to.

<figure class="tiny">
  <img src="{{ site.url }}/images/gulpjs.png">
  <figcaption></figcaption>
</figure>


**[Gulp](http://gulpjs.com/) is a task automator.**  - In the coding terms at least. It automates all the boring tasks like bunching together the assets in your project, bundling them up for deployment, minifying them and more. You can think of it **as your private butler that iterates over a list of chores that you have predefined** on a piece of paper (your `gulpfile.js`). These tasks can be anything: deleting certain files, compressing certain files, watching files for changes, live-reloading browser after changes, compressing images, compiling sass and less-type pre-processors and so on (there are so many that I cannot list all of them of course).

<div class="note"><a href="http://gruntjs.com">Grunt</a> is an equally powerful task automator (perhaps even more feature-rich) but I prefer the simplicity and ease of use of Gulp.</div>

## Integrate Gulp in Your Project

There's not much in the name of setup here. Since Gulp is built with [Node](http://nodejs.org), you need to have Node installed on your machine alongwith `npm`. Once you have that setup, install Gulp with `npm install -g gulp` (to add Gulp globally) and `npm install gulp --save-dev` (to install Gulp in your project). Then add a file named in your project named `gulpfile.js` (blank for now) and you are set to use Gulp.

See the Gulp package on `npm` site here for more information: [https://www.npmjs.com/package/gulp](https://www.npmjs.com/package/gulp).

### How Gulp Works

There are plenty of articles online to explain this. In simple words though, Gulp has a pool of plugins written on top of it (each to be installed separately after Gulp setup) to help you different tasks. A list of all of them can be found here on the [Gulp site](http://gulpjs.com). You only need to install the ones you need (with `npm install`).

Keep in mind that this will quickly add up to the size of your repository and even version controlling them is not a good idea (since you really don't need to version control these packages). What you can do is to write a `.gitignore` file in your base directory of the repo and add the **node_modules** folder in it (it's can become a really large folder size-wise, so it's advisable to omit it from git).

## How I Setup Gulp On Hardik.org

So I decided to make a use of it here on my site. I was looking to minify my CSS, JS and do some compression on the images I have on my blog. Since these assets load on every pageload of your site, shaving off a few kilobytes from them matters a lot in site performance.

Assets to minify:

1. CSS (since I don't use SASS, I just want basic minifying)
2. JS
3. Images (basic compression on PNGs and JPGs)

Other tasks:

* Check JS for errors (linting)

Here's my `gulpfile.js` to achieve above tasks. Funny thing about the gulpfile is that it's almost self-explanatory.

<pre class="language-javascript" rel="css"><code class="language-javascript" rel="css">
var gulp = require('gulp');
var concat = require('gulp-concat'); // concatanate to a file
var rename = require('gulp-rename'); // rename a file
var jshint = require('gulp-jshint'); // check JS code for errors
var uglify = require('gulp-uglify'); // minify JS
var minifycss = require('gulp-minify-css'); // minify CSS
var del = require('del'); // delete files
var notify = require('gulp-notify'); // notify in Terminal with a msg
var imagemin = require('gulp-imagemin'); // compress images
var pngquant = require('imagemin-pngquant'); // compress PNGs

gulp.task('js', function() {
  return gulp.src('js-src/*.js') // get all .js files
  .pipe(concat('all.js')) // add them all together
  .pipe(gulp.dest('js')) // put it in a diff directory
  .pipe(rename({suffix: '.min'})) // add .min suffix
  .pipe(uglify()) // minify (uglify)
  .pipe(gulp.dest('js')) // put it in the destination directory
  .pipe(notify({ message: 'JS task complete' })); // output success message
});

gulp.task('image', function () {
  return gulp.src('images-src/*') // get all images (png, jpg, jpeg, svg, gif)
  .pipe(imagemin({
  progressive: true,
  svgoPlugins: [{removeViewBox: false}],
  use: [pngquant()]
})) // compress all images (you can change this part to your wish)
  .pipe(gulp.dest('images')) // put the compressed images in new folder
  .pipe(notify({ message: 'Image task complete' })); // success message
});

gulp.task('lint', function() {
  return gulp.src('js-src/hvp.js')
  .pipe(jshint()) // check my own JS code for errors
  .pipe(jshint.reporter('default'))
  .pipe(notify({ message: 'Checked JS for errors' }));
});

gulp.task('clean', function(cb) {
  del(['images-src/*'], cb); // delete images from image-src so the same images don't get compressed the next time
});

gulp.task('css', function() {
  return gulp.src('css-src/*.css') // same process as js uglify above
  .pipe(concat('style.css'))
  .pipe(gulp.dest('css'))
  .pipe(rename({suffix: '.min'}))
  .pipe(minifycss())
  .pipe(gulp.dest('css'))
  .pipe(notify({ message: 'CSS task complete' }));
});

gulp.task('default', ['css', 'js', 'lint', 'images', 'clean']); // always execute these on `gulp`
</code></pre>

So this is the Gulp setup for my Jekyll blog:

<figure class="normalised">
  <img src="{{ site.url }}/images/gulpjs-setup.jpg">
  <figcaption>My Gulp workflow</figcaption>
</figure>

That's pretty much it. The modules added using `require` in the beginning of the file are the ones we use and you have to install each one of them separately. It's advisable to have a `package.json` alongside your `gulpfile.js` and have them all install as a bundle in one shot with `bundle install`. I use `notify()` module to inform me when a certain task has finished executing in the Terminal.

In the end, when I am ready, I will execute `gulp` inside my directory and it will execute the `default` task which executes the tasks named `css` and `js` (named so for convenience). It will finish executing in a few seconds and will output the assets in respective directories (defined in the code itself). This is just the surface of what Gulp can do (and the best use case as well). You can find a lot of other smart workflows on the Internet built around Gulp.

### Helpful Links

* [Getting started with Gulp as a complete beginner](http://travismaynard.com/writing/getting-started-with-gulp)
* [Another very good walkthrough on Gulp](http://markgoodyear.com/2014/01/getting-started-with-gulp/)
* [Automating image optimization with Gulp](http://www.devworkflows.com/posts/adding-image-optimization-to-your-gulp-workflow/)
* [Minifying site resources and effect on pagespeed](https://developers.google.com/speed/docs/insights/MinifyResources)
* [`gulp-imagemin` on Github](https://github.com/sindresorhus/gulp-imagemin)
* [Searchable list of all Gulp plugins](http://gulpjs.com/plugins/)

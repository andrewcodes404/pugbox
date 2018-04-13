
A PugBox to play in. To get the html and sass down before converting to pug to use in express
Also some other stuff like for the sass, css, js, fonts image if you like

Remember
----------
To run, cd to this dir and just type 'gulp' in the CLI
To build the dist dir type  'gulp build' in the CLI

There is an image convertor, it's doing something to reduce the size by a little bit but it isn't re-sizing them or anything??
https://www.npmjs.com/package/imagemin

The gulpfile.js
----------------
-* Gulp converts the sass so no need to do it in the CLI

-* useref is where the js and css is compiled and minimised

    -> Turn on/off minify css
      ```js
      // minify css
      // .pipe(gulpif('*.css', cssnano()))

      //or don't minify
      .pipe(gulpif('*.css', gulp.dest('dist/css')))
      .pipe(gulp.dest('dist'));
      ```


If you want to have some local fonts connect to them in a sass file something like _7_fonts.scss
Download them from google fonts or wherever and convert them here --> https://transfonter.org/
You'll get a css file that looks like this
Don't forget to put the fonts in the font dir and
You can also change the gulpfile.js to copy them over to the dist dir

```css
  /* raleway-regular - latin */
  @font-face {
    font-family: 'Raleway';
    font-style: normal;
    font-weight: 400;
    src: url('/fonts/Raleway/raleway-v11-latin-regular.eot'); /* IE9 Compat Modes */
    src: local('Raleway'), local('Raleway-Regular'),
         url('/fonts/Raleway/raleway-v11-latin-regular.eot?#iefix') format('embedded-opentype'), /* IE6-IE8 */
         url('/fonts/Raleway/raleway-v11-latin-regular.woff2') format('woff2'), /* Super Modern Browsers */
         url('/fonts/Raleway/raleway-v11-latin-regular.woff') format('woff'), /* Modern Browsers */
         url('/fonts/Raleway/raleway-v11-latin-regular.ttf') format('truetype'), /* Safari, Android, iOS */
         url('/fonts/Raleway/raleway-v11-latin-regular.svg#Raleway') format('svg'); /* Legacy iOS */
  }
  ```

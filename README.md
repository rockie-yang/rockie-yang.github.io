
This is my personal site on github.io

It is generated with following steps

* install npm, 

brew install npm

* install yeoman, 

npm install -g yo

* install gulp-webapp, 

npm install -g generator-gulp-webapp

* clone the git repository

git clone https://github.com/rockie-yang/rockie-yang.github.io.git

* create site using yo
cd rockie-yang.github.io
yo gulp-webapp

* install gulp-gh-pages plugin
npm install --save-dev gulp-gh-pages

* modify gulpfile.babel.js, add following code
var ghPages = require('gulp-gh-pages');
 
gulp.task('deploy', function() {
  return gulp.src('./dist/**/*')
    .pipe(ghPages({
      branch: "master"
    }));
});

* use it
gulp build
gulp deploy
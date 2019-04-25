# Rhythm

Rhythm is a (work-in-progress) stylesheet that aims to provide easy-to-use typographical alignment to web developers.

## Use

You can either link `css/rhythm.min.css` in your html, or preferably use `scss/rhythm.scss` in your existing Sass workflow.

## Local installation

To install locally:

* `git clone https://github.com/adamrutter/rhythm.git`
* `cd rhythm`
* `npm install`

Three npm scripts are provided:

* `npm run sass` will watch for changes to Sass code in the `scss` directory, and compile it upon any changes.
* `npm run server` will start the live reload server. It uses Browsersync.
* `npm start` will run both of the above scripts.

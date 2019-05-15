# Rhythm

Rhythm is a stylesheet that aims to provide easy-to-use, responsive typographical alignment to web developers.

## Use

Download or clone Rhythm; you can then either link `css/rhythm.min.css` in your html, or preferably use `scss/rhythm.scss` in your existing Sass workflow (you won't add any extra HTTP requests and you'll gain access to variables set within `rhythm.scss`).

## Configuration

Configuration is done within `scss/rhythm.scss`. Maps are used to set your breakpoints, and to configure typography at each named breakpoint.

To configure Rhythm for your project:

### 1. Add breakpoints

Add breakpoints as `key: value` pairs to the `$breakpoints` map:

``` scss
$breakpoints: (
  'default': 0,
  'tablet': 450px,
  'desktop': 700px,
);
```

### 2. Configure breakpoints

Add your breakpoints to the further five configuartion maps (`$base-size`, `$base-line-height`, `$scale-ratio`, `$indent-multiplier`, and `$align-to-grid`) and set values for each:

#### `$base-size`

Sets the base font size for the breakpoint. Used for body type, and to calculate all other sizes.

``` scss
$base-size: (
  'default': 20px,
  'tablet': 18px,
  'desktop': 16px,
);
```

#### `$base-line-height`

The line height for all elements. Used to calculate some other things, too.

``` scss
$base-line-height: (
  'default': 1.3,
  'tablet': 1.4,
  'desktop': 1.5,
);
```

#### `$scale-ratio`

The ratio by which to scale font sizes, used exclusively for headings.

``` scss
$scale-ratio: (
  'default': 1.2,
  'tablet': 1.2,
  'desktop': 1.2,
);
```

#### `$indent-multiplier`

Multiplied by the base font size; to calculate how far elements such as lists and figures should be indented.

``` scss
$indent-multiplier: (
  'default': 1.5,
  'tablet': 2,
  'desktop': 3,
);
```

#### `$align-to-grid`

Align elements to the grid exactly, or allow alignment to half lines. Exact is preferable, but can sometimes introduce bad looking small font-size/high line-height combos.

``` scss
$align-to-grid: (
  'default': 'half',
  'tablet': 'half',
  'desktop': 'half',
);
```

## Functions

To make it easier for you to align elements to the grid in your own stylesheets, Rhythm includes a Sass `function` that returns the line-height at a given breakpoint. `line-height(desktop)` will return the line height for your named `desktop` breakpoint:

``` scss
.my-element {
  margin: line-height(desktop);
}
```

Combining this with your own media queries makes aligning elements to the grid incredibly easy!

## Local installation

You can install locally, if you want to configure Rhythm further:

1. `git clone https://github.com/adamrutter/rhythm.git`
2. `cd rhythm`
3. `npm install`

Three npm scripts are provided:

* `npm run sass` will watch for changes to Sass code in the scss directory, and compile it upon any changes.
* `npm run server` will start the live reload server. It uses Browsersync.
* `npm start` will run both of the above scripts.

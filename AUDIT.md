### Critical css module
This module is used to generate automatic critical css for a HTML & CSS file. It will automatic save it in to another file, which you can later include in your html.


```JS
const critical = require('critical');
```
Use the module inside of the app.

```JS
critical.generate({
    inline: false,
   
    base: 'src/',

    // From:
    src: 'index.html',
    // +
    css: 'src/dist/css/bootstrap.css',
    // =
    dest: 'index-critical.css',

    // enable minify
    minify: true,

    // For viewport CSS
    width: 1300,
    height: 900
});
```
Do the setup.
* Which files are used in the process.
* For which device is it optimised? (viewport)
* Minify the output.

```HTML
<style>{% include 'index-critical.css' %}</style>
```
Include the critical css with the template engine.

### SVG optimization
Is used to deincreasing the file size. This will reduce the SVG load time.
It doesn't only optimize the file size, but it can also increase the readability. 

This tool has a lot of options: (Also included in the interface)
[Options](https://github.com/svg/svgo#what-it-can-do)

<details>
    <summary>SVGOMG Preview</summary>
    <img src="https://iiyama12.github.io/performance-matters/readme-content/SVGOMG.png" alt="svg omg interface">
</details>

[Tool SVGOMG](https://jakearchibald.github.io/svgomg/)

### Minify JS
Is used to deincreasing the file size. This will reduce the page download time.
[Tool JSCompress](https://jscompress.com/)

### Minify HTML
Is used to deincreasing the file size. This will reduce the page download time.
[Tool minifycode](http://minifycode.com/html-minifier/)


### Minify CSS
Is used to deincreasing the file size. This will reduce the page download time.
[Tool minifier](https://www.minifier.org/)

Before:
```CSS
/*!
 * IE10 viewport hack for Surface/desktop Windows 8 bug
 * Copyright 2014-2015 Twitter, Inc.
 * Licensed under MIT (https://github.com/twbs/bootstrap/blob/master/LICENSE)
 */

/*
 * See the Getting Started docs for more information:
 * http://getbootstrap.com/getting-started/#support-ie10-width
 */
@-ms-viewport     { width: device-width; }
@-o-viewport      { width: device-width; }
@viewport         { width: device-width; }
```

After:
```CSS
@-ms-viewport{width:device-width}@-o-viewport{width:device-width}@viewport{width:device-width}
```

### Font optimization

#### Change the font-display

Now the text will be visible in a different font before loading in to the new font. By default on Chrome and Firefox the text will only be visible when the font has been loaded.

```CSS
@font-face {
    font-display: swap;
}
```

#### Changing the css order
Fonts are secondary content, that's why I moved it as last to make sure that it is downloaded/loaded later.

<!-- <link href="/dist/css/fonts.css" rel="stylesheet">  -->
<link href="/dist/css/bootstrap.css" rel="stylesheet">
<link href="/assets/css/src/docs.css" rel="stylesheet">

<!-- \/ -->

<link href="/dist/css/fonts.css" rel="stylesheet">
```





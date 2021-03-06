
# Website optimization

## Github pages
![Github-pages failure](readme-content/github-pages.png)
Github-pages failed...

## Performance update after improvements

See [Lighthouse](https://developers.google.com/web/tools/lighthouse/) performance results:

<details>
    <summary>Performance before</summary>
    <img src="https://raw.githubusercontent.com/IIYAMA12/performance-matters/master/readme-content/performanceBefore.png" alt="Performance before">
</details>


<details>
    <summary>Performance after</summary>
    <img src="https://raw.githubusercontent.com/IIYAMA12/performance-matters/master/readme-content/performanceAfter.png" alt="Performance after">
</details>

<details>
    <summary>Performance critical css</summary>
    <img src="https://raw.githubusercontent.com/IIYAMA12/performance-matters/master/readme-content/critical-css-1.png" alt="Performance critical css">
    <img src="https://raw.githubusercontent.com/IIYAMA12/performance-matters/master/readme-content/critical-css-2.png" alt="Performance critical css">
</details>

<details>
    <summary>Performance minify css</summary>
    <img src="https://raw.githubusercontent.com/IIYAMA12/performance-matters/master/readme-content/css-minify-1.png" alt="Performance minify css">
    <img src="https://raw.githubusercontent.com/IIYAMA12/performance-matters/master/readme-content/css-minify-2.png" alt="Performance minify css">
</details>

<details>
    <summary>Font optimization</summary>
    <img src="https://raw.githubusercontent.com/IIYAMA12/performance-matters/master/readme-content/font-optimization-1.png" alt="Font optimization">
    <img src="https://raw.githubusercontent.com/IIYAMA12/performance-matters/master/readme-content/font-optimization-2.png" alt="Font optimization">
</details>

<details>
    <summary>Image optimization</summary>
    <img src="https://raw.githubusercontent.com/IIYAMA12/performance-matters/master/readme-content/image-opti-1.png" alt="Image optimization">
    <img src="https://raw.githubusercontent.com/IIYAMA12/performance-matters/master/readme-content/image-opti-2.png" alt="Image optimization">
</details>

<details>
    <summary>JS minify</summary>
    <img src="https://raw.githubusercontent.com/IIYAMA12/performance-matters/master/readme-content/js-minify-1.png" alt="JS minify">
    <img src="https://raw.githubusercontent.com/IIYAMA12/performance-matters/master/readme-content/js-minify-2.png" alt="JS minify">
</details>


## Improvements

### Async css loading


```HTML
    <link rel="preload" href="/dist/css/bootstrap.css" as="style" onload="this.onload=null;this.rel='stylesheet'">
    <noscript><link rel="stylesheet" href="/dist/css/bootstrap.css"></noscript>
    
    <link rel="preload" href="/assets/css/src/docs.css" as="style" onload="this.onload=null;this.rel='stylesheet'">
    <noscript><link rel="stylesheet" href="/assets/css/src/docs.css"></noscript>

    <link rel="preload" href="/dist/css/fonts.css" as="style" onload="this.onload=null;this.rel='stylesheet'">
    <noscript><link rel="stylesheet" href="/dist/css/fonts.css"></noscript>

    <script src="assets/js/css-loading.js"></script>
```

```JS
window.addEventListener("load", (e) =>  {
    window.loadCSS("/dist/css/fonts.css");
    window.loadCSS("/assets/css/src/docs.css");
    window.loadCSS("/dist/css/bootstrap.css");
});
```

This code will make sure that the css is downloaded after the window has been loaded.

For more information see: [loadCSS](https://github.com/filamentgroup/loadCSS)



### Critical css module
This module is used to generate automatic critical css from a HTML & CSS file. It will automatic save it in to another file, which you can later include in your html.


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
    <img src="https://raw.githubusercontent.com/IIYAMA12/performance-matters/master/readme-content/SVGOMG.png" alt="svg omg interface">
</details>

[Tool SVGOMG](https://jakearchibald.github.io/svgomg/)

### Minify JS
Is used to deincreasing the file size. This will reduce the page download time.
[Tool JSCompress](https://jscompress.com/)

### Minify HTML
Is used to deincreasing the file size. This will reduce the page download time.
[Tool minifycode](http://minifycode.com/html-minifier/)

Before:
```HTML
<ul class="nav navbar-nav">
    <li>
        <a href="../getting-started/">Getting started</a>
    </li>
    <li>
        <a href="../css/">CSS</a>
    </li>
    <li>
        <a href="../components/">Components</a>
    </li>
    <li>
        <a href="../javascript/">JavaScript</a>
    </li>
    <li>
        <a href="../customize/">Customize</a>
    </li>
</ul>
```

After:
```HTML
<ul class="nav navbar-nav"> <li> <a href="../getting-started/">Getting started</a> </li> <li> <a href="../css/">CSS</a> </li> <li> <a href="../components/">Components</a> </li> <li> <a href="../javascript/">JavaScript</a> </li> <li> <a href="../customize/">Customize</a> </li> </ul>
```

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

```HTML
<!-- <link href="/dist/css/fonts.css" rel="stylesheet">  -->
<link href="/dist/css/bootstrap.css" rel="stylesheet">
<link href="/assets/css/src/docs.css" rel="stylesheet">

<!-- \/ -->

<link href="/dist/css/fonts.css" rel="stylesheet">
```






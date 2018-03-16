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




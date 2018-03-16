# Performance matters

## Project setup

This project serves an adapted version of the [Bootstrap documentation website](http://getbootstrap.com/). It is based on the [github pages branche of Bootstrap](https://github.com/twbs/bootstrap/tree/gh-pages). 

Differences from actual Bootstrap documentation:

- Added custom webfont
- Removed third party scripts
- The src directory is served with [Express](https://expressjs.com/).
- Templating is done with [Nunjucks](https://mozilla.github.io/nunjucks/)

## Getting started

- Install dependencies: `npm install`
- Serve: `npm start`
- Expose localhost: `npm run expose`



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

```CSS
<!-- <link href="/dist/css/fonts.css" rel="stylesheet">  -->
<link href="/dist/css/bootstrap.css" rel="stylesheet">
<link href="/assets/css/src/docs.css" rel="stylesheet">

<!-- \/ -->

<link href="/dist/css/fonts.css" rel="stylesheet">
```


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
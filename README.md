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


### Compress images
To speed up the content, all images are re-compressed for the web. The default image compressors within for example Photoshop do not compress to this level by default. You can do it in Photoshop ofcourse, but you need to have some advanced knowlegde about everything related to images. In Photoshop you can for example reduce the amount of colors, but that is only helpful depending on the end format. 

Tools online like Tinypng can do this automatic for you. 

The images of this website are compressed with: https://tinypng.com/

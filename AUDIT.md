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
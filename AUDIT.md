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



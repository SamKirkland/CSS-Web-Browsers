# CSS Web Browsers

[Demo](http://samkirkland.com/labs/CSS-Web-Browsers/browsers.html)

## Description:

Web Browsers based entirely on CSS without images.

Custom browser styles for Firefox, Safari (coming soon), Edge (coming soon), Chrome, and Internet Explorer.

## Source:

Version: v0.02
Released: 2015-08-21

Hosted at GitHub; browse at:
https://github.com/SamKirkland/CSS-Web-Browsers

## Usage:

1. Copy the contents of css/ to the css asset directory in your project.
``* (optionally) use scss and compile it after changing variables to meet your needs.

2. Include the required CSS into your document:
```html
<link rel="stylesheet" type="text/css" href="css/normalize.min.css" />
<link rel="stylesheet" type="text/css" href="css/cssWebBrowsers.min.css" />
```

3. Add the HTML to your document.
<div class="miniBrowser">
<div class="miniBrowserHeader">
<ul>
<li class="close"></li>
<li class="minimize"></li>
<li class="expand"></li>
<li class="tab activeTab firstTab">Tab 1</li>
<li class="tab">Tab 2</li>
<li class="newTab">+</li>
</ul>

<div class="miniBrowserToolBar">
<div class="miniBrowserBack"></div>
<div class="miniBrowserForward"></div>

<div class="refresh"></div>
<div class="home"></div>

<div class="miniBrowserURL https">
<div></div><input type="text" spellcheck="false" value="https://samkirkland.com/">
</div>

<div class="menu"></div>
</div>
</div>
<div class="miniBrowserContent">
Place Content Here
</div>
</div>

4. Customize the HTML or add a browser specific class to the root <div class="miniBrowser"> element:
``* .firefox
``* .safari (coming soon)
``* .edge (coming soon)
``* .chrome
``* .ie

5. (Optional) Add Javascript to autodetect the users current browser and style the default browser to match their current web browser:
```js
/* This wont work all the time, but its good enough */
function detectBrowser() {
var browser = "";
var userAgent = navigator.userAgent.toLowerCase();

// is internet explorer
if (userAgent.indexOf('msie') > -1 || userAgent.indexOf('edge') > -1 || userAgent.indexOf('trident') > -1) { browser = "ie"; }

// is firefox
else if (userAgent.indexOf('firefox') > -1) { browser = "firefox"; }

// is chrome
else if (userAgent.indexOf('chrome') > -1) { browser = "chrome"; }

// is safari
else if (userAgent.indexOf('safari') > -1) { browser = "safari"; }

return browser;
}

// waits for the DOM to finish loading
document.addEventListener("DOMContentLoaded", function(event) {
// adds the current browser class to the first occurance of .miniBrowser 
document.getElementsByClassName("miniBrowser")[0].className = "miniBrowser " + detectBrowser();
});
```

## License:

Copyright 2015 Sam Kirkland (mailto:css-web-browsers@samkirkland.com)
Released under The MIT License.
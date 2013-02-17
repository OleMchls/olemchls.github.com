---
title: Cloud-Zoom inside Fancybox
author: Ole Michaelis
layout: post
categories:
  - One Step
tags:
  - Cloud-Zoom
  - FancyBox
  - JavaScript
---

Hey there,
*I like to translate this post to english, due to this awesome interest.*

Today I want to blog some programming stuff, its some time ago I do that. I give my attentaion to the cowork of fanybox and cloud-zoom, booth are jQuery plugins. And to be honest it’s not that hard as it sounds. Let’s go:

Fancybox init:

```javascript
$(“a.gallery”).fancybox({
‘onComplete’ : function(arg) {
// Here does the magic starts
$(‘#fancybox-img’).wrap(
$(‘‘)
.attr(‘href’, $(arg[0]).attr(‘href’))
.addClass(‘cloud-zoom’)
.attr(‘rel’, “position: ‘inside’”)
);
// That’s it
$(‘.cloud-zoom’).CloudZoom();
}
});
```
Now deactivate the boarders in cloud-zoom.css:

```css
/* This is the zoom window. */
.cloud-zoom-big {
/*border:4px solid #ccc;*/
overflow:hidden;
}
```

Thats it. Have fun!


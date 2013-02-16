---
title: Change URL without reload
author: Jan Scheurer
layout: post
permalink: /2011/change-url-without-reload/
dsq_thread_id:
  - 750996769
categories:
  - JavaScript
tags:
  - HTML5
  - JavaScript
  - Pushstate
---

Hello and welcome to the show ;)

I’m the new guy in the hood, i’ll also mostly talk about javascript development, maybe some server-side stuff and, if somebody cares, also 3D related stuff. Alright lets hit it.

We all know and use it, facebook. As a webdeveloper you may have noticed that the “main content area”(where the posts are) is the only part that reloads. **It’s AJAX**, damn you already knew that?! Ok, but you may asked your self how they’re changing the URL without a reload. I can tell you,this it not the all so mighty web 2.0 ajax magic thing. The stuff we are talking about is cooler, a lot cooler, it’s this experimental stuff, this “you can do everything, and more, in the browser without plugins” – **HTML5**.

So if you’re developing with browser compatibility in mind, take a second look at the url on facebook. It has a questionmark in the beginning, so PHP will parse these URL too. On the one hand it’s to be compatible with those other browsers on the other hand you need this for users who are browsing directly to one of those subpages.

“*Stop talking and show me how it works!*”

Alright!

You may think it has something to do with the window.location object. Sorry, it’s not! The object we’re looking at now is the window.history object.

```javascript
window.history.pushState(
{
‘test’:”oh i am a test text :O”,
‘stuff’:”some stuff here”
},”History title”,”/?changed”);
```

So what do we have here?

The first parameter is an object which we’ll parse later, the second one is simply the name of the state and the third and last one is the new url. You can also change the whole url by starting with “http://” but same origin policy will prevent you from doing malicius stuff with it.

So lets go one step further and parse this object and also detecting and reacting on state changes.

```javascript
window.onpopstate = function(event){
alert(event.state.test);
alert(event.state.stuff);
}
```

So i think this is pretty self explanatory, the onpopstate event get triggered if you move forward or backward in your browser history.
The state object contains the stuff you pushed in there. You’ll also find the state name somewhere in the event object.

I hope you enjoyed the read and we’ll see us again.
Follow me @[twitter][2] if you want to get news about WebGL and gamedevelopment related topics
and stay tuned to this blog for bleeding edge web technology informations.

 [2]: http://twitter.com/#!/LJ_1102 "twitter"

see ya!
---
title: 'Inner &#8216;Classes&#8217; in JavaScript'
author: Ole Michaelis
layout: post
dsq_thread_id:
  - 752962434
categories:
  - JavaScript
  - One Step
tags:
  - InnerClasses
  - JavaScript
  - PHP2JS
  - Tutorial
---

Hey there,

**The first post in 2011. So happy new year to all of you!**

The last days I played around with JavaScript, it’s a very cool language, and this post should be the first a few JavaScript OOP tutorial posts. And I want to start with a little example for inner classes in JavaScript. Okok, you all know there are no classes in JavaScript, so there couldn’t be inner classes. But the known behavior of inner classes like in Java could be ported to JavaScript. Lets see…

In this example we have a little Object/Class/Function, whatever ;) which loads HTML templates from a Server with AJAX, and to prevent multiple ajax calls to the same template, I want to have a little cache (Note: I you have configured your web server right, it’ll answer *304 NOT MODIFIED*, but we also want to save the request. [If you want to learn more about configuring your webserver the right way, read my articles about performance optimization for a Apache web server][2])﻿﻿.

 [2]: http://blog.codestars.eu/category/speed_up/ "It's in German, but if any1 is really interested in it. I'll translate it!"

But lets take a look at the code:

```javascript
var TemplatingStuff = function(){
/** some code **/
var cache = new function(){
var cacheData = {};
this.set = function(name, data){
cacheData[name] = data;
};
this.get = function(name){
return cacheData[name] || false;
};
this.deleteEntry = function(name){
cacheData[name] = undefined;
};
this.flush = function(){
cacheData = {};
};
};
/** some code **/
}
}
```

Yeah thats it, define a function as usual and add a new in front of it, and assign it to a var, so you can use your cache in the rest of the ‘object’/class/function, whatever ;) And of cause you can also use it with prototyping, but here its public, not private like in the first example.

```javascript
TemplatingStuff.prototype.cache = new function(){
var cacheData = {};
this.set = function(name, data){
cacheData[name] = data;
};
this.get = function(name){
return cacheData[name] || false;
};
this.deleteEntry = function(name){
cacheData[name] = undefined;
};
this.flush = function(){
cacheData = {};
};
};
```

Ohh and if you’re curious what I’m doing there with templating stuff in JavaScript, be prepared. Maybe I’ll publish it later, just let me say; I’ll call it UrgeEngine.

See Ya!
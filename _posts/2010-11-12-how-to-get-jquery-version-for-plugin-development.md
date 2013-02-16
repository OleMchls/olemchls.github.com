---
title: How to get jQuery Version for plugin development
author: Ole Michaelis
layout: post
permalink: /2010/how-to-get-jquery-version-for-plugin-development/
dsq_thread_id:
  - 752948569
categories:
  - One Step
tags:
  - JavaScript
  - jQuery
  - plugin development
  - plugins
---

Hey there,

Today I want to update to jQuery 1.4.4 but there was a Problem, with my self written fadeToggle() Plugin, due to this problem I have to find out which jQuery version the Plugin User has. And while I try to find an answer via Google, I recognize that there was no real answer for that. So I took a look into the jQuery source, and there was the answer:

```javascript
// The current version of jQuery being used
jquery: “1.4.4″,
```

This is one attribute of the jQuery Object. But this is a String… So how should I check against a String, I dont want do check for a Special version, I want so check if the Used source version is greater then another. But we already have the string so it shouldn’t be that harx to find it out. And to be honest, it isn’t that hard :) Just a bit JavaScript magic:

```javascript
if (parseInt($().jquery.replace(/./g,”)) > 144)  {
…
}
```

Here i checked against the jQuery version *1.4.4* if you want to check against for example *1.2.1* it “*121*” but here Cpt. Obvious was at work. Ok just kidding, thats all.

See Ya!
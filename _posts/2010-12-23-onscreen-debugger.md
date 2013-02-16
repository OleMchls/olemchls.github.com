---
title: On-Screen debugger for JavaScript
author: Ole Michaelis
layout: post
permalink: /2010/onscreen-debugger/
dsq_thread_id:
  - 793095041
categories:
  - One Step
  - Tools
tags:
  - debugger
  - html debugger
  - JavaScript
  - javascript debugger
  - Onscreen
---

Hey folks,

Today I want to show you a little nice tool which I coded today, it’s not *eyeflashing-hardcore-awesomeness* BUT its nice! ![:)][1] Do you ever saw a desktop gamedeveloper during his work? They mostly have debug output on their screen. Like FPS or s.th. depinding on their needs. They just push string to the upper (mostly left) corner.

 [1]: http://blog.codestars.eu/wp-includes/images/smilies/icon_smile.gif

I’m not a **desktop** game developer, but I wanna have such a tool, too. So I take a few hours and made one, and its cool. Want to see a demo? Here it is:

Nice, isn’t it?

And it’s really easy to use, look

```javascript
made it accessible in global scope
and give a target (in jQuery notation)
var vConsole = new visualconsole(‘debug’);
now you can use it like this
vConsole.log(“foo”);
vConsole.log(“bar”, ‘bazID’);
vConsole.update(‘bazID’, ‘foobar’);
```

For me the most important feature is that not like the browser console. Which creates a new line for every entry, you can update existing entries. As you can see in the example the mouse position on the site.[![VisualConsole UML][2]][2]
VisualConsole UML

 [2]: /assets/uploads/2010/12/visualconsole.png

And yeha we’re so used to UML so I’ll offer a UML for this too. Greets to my Classmates ![;)][3]

 [3]: http://blog.codestars.eu/wp-includes/images/smilies/icon_wink.gif

But there are a few things to note, first this tool requires jQuery, only strings can be displayed correctly and note there’s no scrolling in it. But feel free to add it, I will add it as soon as I needed it ![:)][1] Ohh and I nearly missed it to give you the download: **broken**

Hope you enjoy it. If you do, don’t forget to share this with all your friends via twitter or share it on Facebook


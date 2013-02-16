---
title: Profiling with WebKit
author: Jan Scheurer
layout: post
permalink: /2011/profiling-with-webkit/
Hide SexyBookmarks:
  - 0
wp_plus_one_redirect:
  - 
Hide OgTags:
  - 0
dsq_thread_id:
  - 743504372
categories:
  - JavaScript
  - Speed Up!
tags:
  - api
  - Chrome
  - Chromium
  - Inspector
  - JavaScript
  - Performance
  - Profiling
  - Safari
  - WebKit
---
# 

Hello again!  
If you follow me on twitter you’ve already noticed that I took a look into the Chromium source.  
I was searching for a way to profile specific code snippets.  
I asked google for the WebKit Inspector Profile API with no result.  
So i digged around in the WebKit Inspector code and found out how it works.

[javascript]  
console.profile(“Hard Calculations”);  
// the script you want to profile  
console.profileEnd();  
[/javascript]  
Pretty easy, huh?* “Hard Calculations”* is the name of the profile that will be created.  
Btw. if you run this in the console itself you’ll only see injection functions so try it in your project.

Hope this was helpful for you.  
Have a nice day!


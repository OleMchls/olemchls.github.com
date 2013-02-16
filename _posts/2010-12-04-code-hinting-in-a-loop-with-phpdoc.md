---
title: Code hinting in a loop with PHPDoc
author: Ole Michaelis
layout: post
permalink: /2010/code-hinting-in-a-loop-with-phpdoc/
dsq_thread_id:
  - 759393186
categories:
  - One Step
tags:
  - Code hinting
  - IDE
  - loop
  - PHP
  - PHPDoc
---
# 

Hey there,

I want to continue bloggin’ technical and programming stuff, so these time I want to talk about code hinting / auto completetion in a loop with [PHPDoc][1].

 [1]: http://www.phpdoc.org/

I think you all knew this problem: you store one kind of object in an array. You iterate over this array and want to execute some methods of this object, but due to the loose typing of PHP your IDE cant give any type hints or auto completetion. A few days ago I had the same problem, I wanna have some kinda auto completetion in my IDE, cuz I’m lazy (BITCH!) ![:)][2] .

 [2]: http://blog.codestars.eu/wp-includes/images/smilies/icon_smile.gif

I asked my friend Google and I found some answers, but they are all not that “complete” as I searched for. So I wanna try to give these kinda complete answer to this question, with example code. The answer is really simple, just use PHPDoc in the loop to tell your IDE with kinda object stored in this var.

[php]  
/* @var $bar bar */  
[/php]

Easy, heh?

And the result is AWESOME (more or less ![;)][3] )

 [3]: http://blog.codestars.eu/wp-includes/images/smilies/icon_wink.gif

[![Autocompletetion in a loop!][5]][5]
Code Hinting in a foreach

And the complete example you’ll find here: [download id="2"]

 []: http://blog.codestars.eu/wp-content/uploads/2010/12/loop_code_suggestion.png

See ya!


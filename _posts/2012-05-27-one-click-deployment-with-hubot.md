---
title: 'One-click-deployment with Hubot &#8211; Hubot: my new mate, co-worker and devops engineer'
author: Ole Michaelis
layout: post
permalink: /2012/one-click-deployment-with-hubot/
Hide SexyBookmarks:
  - 0
Hide OgTags:
  - 0
wp_plus_one_redirect:
  -
dsq_thread_id:
  - 743615073
categories:
  - Digital Pioneers
  - OpenSource
tags:
  - CoffeeScript
  - Hubot
  - JavaScript
  - Scalarium
---

Do you know “Hubot”? This awesome robot build by the github guys?

[![Hubot][1]][1]
Hubot

No? Srsly? Ok you should meet him – [here][2] - now!

 [1]: /assets/uploads/2012/05/Screen-Shot-2012-05-27-at-9.51.53-AM.png
 [2]: http://hubot.github.com/

Ok now you might have a clue what he’s doing now? Some toy for man, heh? But no honestly he can do much MUCH more. He’s some kind of a friend, he slaps you when you use [inappropriate language][3], replies to [your questions][4] or just let you [waste some time with 9gag][5]. And there is more, it’s up to you to train him [new stuff][6]. Let him do the stuff you hate to do, [pick][7] a pizza delivery service, decide for [a nice song][8] or even let him deploy you app!

 [3]: https://github.com/github/hubot-scripts/blob/master/src/scripts/demolition-man.coffee
 [4]: https://github.com/github/hubot-scripts/blob/master/src/scripts/talkative.coffee
 [5]: https://github.com/github/hubot-scripts/blob/master/src/scripts/9gag.coffee
 [6]: https://github.com/github/hubot-scripts#writing
 [7]: https://github.com/github/hubot-scripts/blob/master/src/scripts/decide.coffee
 [8]: https://github.com/github/hubot-scripts/blob/master/src/scripts/play.coffee

And this is what I wan’t to talk about. We at Digital Pioneers use [Scalarium][9] to manage our AWS hosted apps. With scalarium you first define an could, define different roles, like Webserver, Loadbalancer and Databases. You can assign apps to the clouds and then do some common tasks on the app or on the cloud. Like deploy the application, reboot an webserver or add an extra webserver for better scaling. You can do all the stuff on the scalarium website or use the [api][10].

 [9]: http://www.scalarium.com/
 [10]: http://support.scalarium.com/kb/api/

We want some of kind one-click-deployment. On the scalarium website an deploy is more then just one click and the session expires pretty fast, so deploying on the scalarium website is kind of annoying. So I took the chance to learn some thing new, **CoffeeScript** (hubot scripts are written in CoffeeScript). I wrote a little ApiClient for scalarium and connected it to hubot. So now we’re able to deploy within our developer chat. This looks like this:

[![Hubot deploy][11]][11]
Hubot deploy

This is pretty awesome heh? And because we at Digital Pioneers love Open Source, we will give some love back to the community. So here’s the hubot script: . I’ll contribute the script back to [hubot-scripts][12] after we some how tested it b/c as far as i noticed yet it’s a lil bit buggy. And not that feature complete as i would like to have it.

 [11]: /assets/uploads/2012/05/Screen-Shot-2012-05-27-at-10.19.19-AM.jpg
 [12]: https://github.com/github/hubot-scripts

The bot is also able to list app and clouds, but this features are not that amazing like the deployment thingy, just want to mention it here, to be complete ![:)][13]

 [13]: http://blog.codestars.eu/wp-includes/images/smilies/icon_smile.gif

What about you? You also love OpenSource? You also love these devops thingy? **[WE ARE FUCKING HIRING!][14]** We’re serious, we are looking for you as an *DevOps Engineer* or *Software Developer*! So come on and be my co-worker and join Digital Pioneers N.V.!

 [14]: http://digitalpioneers.de/jobs/

 

UPDATE **May 30, 2012**

This scripts got finally fully merged into hubot-scripts (). So please feel free to contribute, use and love it!


---
title: 'Jimdo and jekyll'
author: Ole Michaelis
layout: post
categories:
  - Jimdo
  - jekyll
tags:
  - jimdo
  - jekyll
  - Blog
---

Ohh boy! Such a long time passed since the last post. I just wonna give all of you a few updates.

> TL;DR
> I'm now working for [Jimdo][jimdo].
> This blog now runs with [jekyll][jekyll] and [github pages][gh_pages].
> Please change your reader to [http://feeds.feedburner.com/Codestars][feedburner].

### I'm a Jimdo'er

[![Jimdo-Team][jimdo-team-pic]][jimdo-team-pic]

If you follow me on [twitter][codestars] you might noticed that I recently changed my employer! I now work for [Jimdo][jimdo], again in Hamburg. If you wonder what Jimdo is or does?! - I always describe Jimdo like this:

> We make your mama' creating websites, unless she isn't already a webdeveloper

I'm at the infrastructure team at the moment, so doing lots of devops stuff there. You wonna know why I switched? Just meet me in person the next meetup or conference!

### A complete new blog
As you might notice, this blog completely changed! I started with this blog back in 2009 on my own vServer at a very crappy hoster (1Blu - sorry, but no recommendation here). I don't want to administrate all the stuff which comes along with having your own server. Like doing system updates, manage wordpress and plugins. Plus having such a crappy coded blog-engine like wordpress. I don't wonna touch any wordpress code, so no chance for me to make changes to the blog-engine.

I discovered [jekyll][jekyll], [octopress][octopress] and stuff one or two years ago and together with [github:pages][gh_pages] this looks very promising to me. So I want to switch since... ever. But didn't have the <strike>time</strike> guts to really do it! Last weekend I want to write a new blogpost, so I logged into my wordpress and started ... with installing updates, as always. At this point I decided to finally make the switch-over! Therefore I defined what to do:

* take care of the comments
* split-up domains from vServer
* export and transform posts
* setup jekyll and github pages

Let's check step by step

#### take care of the comments
This was an easy pick for me, b/c I already switched to [disqus][disqus] a few month ago in preparation for this switch. Just install the disqus wordpress plugin and transfer you comments. This is a no-brainer srsly!

#### split-up domains from vServer
Ohh man! Not that no-brainer as I hoped it will be. As I mentioned my old hoster was really crappy and one goal of the move was to get rid of the contract. After I met [Anthony Eden][aeden] the man behind [DNSimple][dnsimple] at the [TakeOff Conference][takeoff] in Lille( and [he pooped][aeden-poopin] [me][aeden-poopin2]). I obviously had to switch my domains to them. And man, I really love this service. I love *everything-as-a-service* in general and they are a really perfect match for this kind of things!

#### export and transform posts
The ease of this task __really__ depends on your existing post and the fancyness in there. I just followed this guy [http://weedygarden.net/2012/12/hello-jekyll/][hello-jekyll]

I had a couple of embedded youtube videos and other iframes - and they all break. But with some sed/awk and search and replace I fixed most of them. But you will definitely find some broken posts in the archive.

#### setup jekyll and github pages
I suggest any wrapper around [jekyll][jekyll] like [jekyll bootstrap][jb] or [octopress][octopress] unless you really want to build up everything from scratch on your own.

So yeah - here it is! My fresh, new, shiny blog crafted with jekyll bootstrap and github pages. It's now responsive, fast, supercool and nerdy. Plus I think this will encourage me to blog more in 2013!

Oh and if you are following my blog on your reader: Please change your reader to [http://feeds.feedburner.com/Codestars][feedburner].

 [jimdo-team-pic]: /assets/uploads/2013/02/jimdoHQ.jpg
 [codestars]: https://twitter.com/codestars
 [jimdo]: http://jimdo.com/
 [jekyll]: http://jekyllrb.com/
 [octopress]: http://octopress.org/
 [jb]: http://jekyllbootstrap.com/
 [gh_pages]: http://pages.github.com/
 [disqus]: http://disqus.com/
 [aeden]: https://twitter.com/aeden
 [dnsimple]: https://twitter.com/dnsimple
 [takeoff]: http://takeoffconf.com/
 [aeden-poopin]: https://twitter.com/CodeStars/status/291621090390843392
 [aeden-poopin2]: http://storify.com/CodeStars/conversation-with-codestars-and-aeden
 [hello-jekyll]: http://weedygarden.net/2012/12/hello-jekyll/
 [feedburner]: http://feeds.feedburner.com/Codestars

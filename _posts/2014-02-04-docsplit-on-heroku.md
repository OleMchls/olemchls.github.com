---
layout: post
title: "Docsplit on heroku"
description: ""
tech: true
categories:
  - OpenSource
  - Development
tags:
  - tech
  - docsplit
  - heroku
  - buildpacks
---
{% include JB/setup %}

I often search the web for things! But in roughly 20% of the cases even google don't have the answer to my very specific question. And also due to that fact that a lot of traffic comes trough search engines I would like to blog more often tech stuff. So lets go!

For my side project [slidr.io](http://slidr.io) I choose heroku as a platform, because hardware sucks. But it's (beside my current work project) it's my first "real" thing on heroku I sometime stumble upon things I have no clue how to solve it in heroku-candyland. Like recently I wanted to use [Docsplit](http://documentcloud.github.io/docsplit/) a gem which had a dependencies to some system packages.

After searching the web for quite a while I found 'build packs' will be the solution for that. But I needed more packages and build packs usually only fulfill one dependence. So we need the [multi-buildpack](https://github.com/ddollar/heroku-buildpack-multi). You can use it for your current app like that.

```bash
$ heroku config:add BUILDPACK_URL=https://github.com/ddollar/heroku-buildpack-multi.git
```

Now you can go ahead and search the web (or basically github) for all the build packs you need for docsplit to run and put them into your `.buildpacks` which should be located in your projects root.

```bash
λ  slidr.io git:(master) ✗ cat .buildpacks
https://github.com/mcollina/heroku-buildpack-graphicsmagick.git
https://github.com/BauCloud/heroku-buildpack-poppler.git
https://github.com/elbongurk/heroku-buildpack-ghostscript.git
https://github.com/heroku/heroku-buildpack-ruby.git
```

My `.buildpacks` looks like this and docsplit runs very fine.

I hope this might also help you, just drop me a line if so or even if you might encounter any issues.

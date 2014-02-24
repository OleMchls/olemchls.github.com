---
title: 'Hubot on nodejitsu'
author: Ole Michaelis
layout: post
tech: true
categories:
  - Hubot
  - JavaScript
  - PaaS
tags:
  - coffeescript
  - robots
  - chatrobot
  - nodejitsu
---

A few weeks ago I finally managed to deploy [Hubot][hubot] on [nodejitsu][nodejitsu], as I've read a few times people want to know how this works, heres my tutorial.

###Prerequisites
First of all you need a deployable version of Hubot

```bash
git clone git://github.com/github/hubot.git
cd hubot && npm install
bin/hubot -c ../deployable_bot
cd ../deployable_bot && npm install
```

Now you have a deployable version of Hubot in the `deployable_bot` folder. Next step would be to [configure your adapter][adapter]. When your done with this, you have a runnable version of Hubot. Now let's move on with the nodejitsu part. I assume you have your account and the cli-tools properly set up.

###nodejitsu and cli flags
As you might have noticed nodejitsu isn't able to take cli flags. But we need them to make Hubot run properly. Luckily we can configure Hubot also via environment variables. So let's move all the needed parameters into the package.json, every cli flag is also available as environment parameter with the `HUBOT_` prefix

```json
{
  "name": "demo-hubot",
  "scripts": {
    "start": "node_modules/.bin/hubot"
  },
  "env": {
    "HUBOT_ADAPTER": "xmpp",
    "HUBOT_NAME": "demobot"
  }
}

```

**note: with nodejitsu you can also store your environment variables in the WebOps interface. Because you'll have a lots of passwords in your environment variables, and I really suggest *not* storing passwords in any repository.**

###deploy on nodejitsu

This is properly the easiest part

```bash
jitsu deploy
```

Your application will be created if it's not there yet. Your robot should now join your configured chat.

###why nodejitsu? when there is already heroku support

Here are a couple of reasons:

* I like new stuff
* nodejitsu is for node
* there are no dynos (so no idle timeout stuff)
* [Zero Downtime Deploys](https://www.nodejitsu.com/documentation/features#zero-downtime-deploys)

###is there more?

Oh yes! [You can have auto-deploy](http://blog.nodejitsu.com/github-continuous-deployment) or check out [Hubot docs](https://github.com/github/hubot/wiki) or [nodejitsu docs](https://www.nodejitsu.com/forward#/docs). Hope you this works for you as good as it does for me. If not, just drop me a [tweet](https://twitter.com/codestars) :)

 [hubot]: http://hubot.github.com/
 [nodejitsu]: https://www.nodejitsu.com/
 [adapter]: https://github.com/github/hubot/wiki/_pages
---
title: 'Could I become an Ops please'
author: Ole Michaelis
layout: post
categories:
  - Development
  - Jimdo
tags:
  - devops
  - jimdo
---

I started at Jimdo December 2012, ready to change everything and bring in all my gained knowledge in Software Design and Service Oriented Architecture (SOA). I already knew that the Jimdo system is approximately six years old, so what we all call a "grown system". In fact this means there are a few thing I would do "better", like we have code tightly coupled to the hardware structure and also into itself. No SOA at all, but I want to change that, as I was hired for the Feature team, I realized pretty fast that I, of cause, can't do it alone. I teamed up with [Sönke](https://twitter.com/s0enke) and joined the Infrastructure team. He is a Jimdo since 4 years, so he knows a lot about the system, but he is also a great software architect.

> Why I joined the Infrastructure team?
Well, I realized that before we can refactor the software we have to do some operations work. Infrastructure team at Jimdo is responsible for two different tasks:

1. **Keep the system running**, we have a bunch of hardware servers, so we have to deal with lot's of disk failures and network issues.
2. **Improve the system**, we are all very annoyed by the things mentioned above. So we can't to get rid of "möhrchenkonzept" (that's how we call it internally) means putting old parts of the system out and putting new stuff in.

Hired as an Open Source Rockstar (or technically speaking "Software Engineer") - I ended up as an Ops guy just a month after I started. This was and still is a great opportunity to learn, not just for me, I'd like to say every developer should do this.

Things I learned:

* **Beeing on-call**, this actually is one of the hardest things I had to learn. As an Ops guy you are FUCKING RESPONSIBLE for the system, not only like when you're in the office or like at the laptop. You should respond to an alarm within a given time, so no partying, no real chance for any activity where you don't can act within a reasonable time. Of cause you also have to get up in the middle of the night. Think about the things our doing over the week, and if you can also do them when you are **on-call.**
* **Deploying to production** can cause a collage to spend the night infront of his laptop. You should develop, as if you have to get up when your deploy cause errors.
* **There's no magic involved**, your code is always running on systems which have, somehow, to be maintained. Of cause you can reduce the amour of work that have to be done with cloud solutions. But these could solutions can only reduce the work which results from hardware stuff. But when you are coding crap even Amazon can't help you. So sorry friends, I know, the truth can hurt. But there's no shiny candy land out there which can execute code.

*This can be a little bit catchy*
For me people never used linux as an operation system are no real developers. It's more then mandatory to know the platform your code is running on, as I mentioned above. And most of our all apps are hosted on an whatever linux distribution. I'm also a Mac user, but before I switched to Apple I used Ubumntu for quite a long time. And this now helps me a lot, so I at least know the basics in operations business.

So grab your ops colleagues and maybe offer them a little position exchange (everything included, also being on-call) for about a week or so. You will see this will change your mind and you will gather some more insights and gain a better understanding of the so called "system administrators" in your company. Oh and I finally learned some puppet, too.

Sidenote: If you like this topic and want to hear more of this, I will give [a Talk on this topic](http://www.thatconference.com/sessions/speaker_Ole_Michaelis) at [ThatConference](http://www.thatconference.com/) in Wisconsin this August. If you're also curious about this topic please step by and let's have a talk.

Jimdo also have a [Developers Blog](http://dev.jimdo.com) you definitely should follow. We try to blog about more specific things we archived so far.
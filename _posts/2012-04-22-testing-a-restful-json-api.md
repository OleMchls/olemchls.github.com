---
title: Testing a restful JSON API
author: Ole Michaelis
layout: post
permalink: /2012/testing-a-restful-json-api/
Hide SexyBookmarks:
  - 0
Hide OgTags:
  - 0
wp_plus_one_redirect:
  -
dsq_thread_id:
  - 746780430
categories:
  - Digital Pioneers
tags:
  - PHP
  - Symfony2
  - Testing
---

Back in blog business, first I want to start with a very few personal words. I left the gaming industries, now I’m working for [Digital Pioneers N.V.][1] there we do rapidly prototyping of new ideas with cool, new shiny techniques!

 [1]: http://www.digitalpioneers.de

At the moment I work on the backend for [Stuffle][2], the client-server communication is done via a restful json api. And here the challende begun. Symfony2 luckily offers very cool techniques to build a restful HTTP api. But as the client is written in a strongly typed language we have to make sure to meet the specified api. And when I say meet I’m fucking serious, a “date” must be and timestamp, nothing easier then that right? But when we as PHP developers take almost everything as a valid timestamp:

 [2]: http://signup.stuffle.it/



Nor in a strongly typed language, there we’ll already come into trouble with the second example. So we have to find a way to make the API very stable even during the development process, because the two parts were developed at the same time. So we decided to develop the API test driven. But have you ever written tests with for stuff like this, I did not before! Luckily we use symfony2 so the first step was to implement a service that transfroms our MongoDB documents (with some other extra dataproviders) into a json string which met the specifications. So almost all of our actions ends like

Now we’ll come to the tricky part. Because if we want to test the whole response including the types and it’s correct we would end in test methods containing around 200 assertions. NO WAY!

So we splinted up the whole thing into it’s parts. First of all we wrote normal UnitTests for the “api.response.json” service, and honestly mocking MongoDB documents sucks hard! And I swear next time I need some thing like that I’ll write an plugin for that. Anyway, that UnitTests make sure that the response is always valid when we’re using this service for the response content.

The other and even bigger part are the integration tests (Symfony WebTestCase). We use fixtures, lots of ‘em. And due to that fact the the UnitTests for this “api.response.json” service make certain that the response is valid regarding the api specs. We just have to check the HTTP response code and maybe some smaller fractional checks for the data in the response.

And yeha, that’s basically it. So the magic is to bundle all the responses to the service. And a little side note when you’re interested in how we’re developing and deploying my college [florian][3] wrote a few articles on [his blog[GER]][4].

 [3]: https://twitter.com/#!/fholzhauer
 [4]: http://fh.vc/


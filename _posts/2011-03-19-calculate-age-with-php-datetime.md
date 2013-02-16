---
title: Calculate age with PHP DateTime
author: Ole Michaelis
layout: post
permalink: /2011/calculate-age-with-php-datetime/
dsq_thread_id:
  - 743519462
categories:
  - One Step
  - PHP
tags:
  - calculate age
  - get age
  - PHP
---
# 

Hey there,

First of all I want to say sorry, that I don’t write anything for such a long time, but I’ve a really big project running and this is why I have no time for blogging at the moment. BUT I want share a little codesnippet with you. The project I mentioned is a big community site and therefor I needed a cool way to get the age from a user, but we only have his birthday. And nearly all solutions google shows me don’t respect the leap-years. So I have to look for a solution on myself. And yeah it’s pretty easy with the “new” PHP DateTime. Take a look:

[php]  
$oDateNow = new DateTime();  
$oDateBirth = new DateTime($sDateBirth);  
$oDateIntervall = $oDateNow->diff($oDateBirth);  
/* @var $oDateIntervall DateInterval */  
echo $oDateIntervall->y;  
[/php]

That’s it. Easy, huh?

The next post in abount two weeks hopefully will announce the “big” project I’m working on. So stay tuned…


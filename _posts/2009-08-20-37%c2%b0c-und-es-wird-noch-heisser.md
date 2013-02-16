---
title: '37°C und es wird noch heisser&#8230;.'
author: Ole Michaelis
layout: post
permalink: /2009/37%c2%b0c-und-es-wird-noch-heisser/
dsq_thread_id:
  - 808949343
categories:
  - One Step
tags:
  - '#Musik'
  - Shit Happens
  - Tools
---

… das ist mein Absoluter Lieblings Singstar Song :) Aber das Wetter ist gar nicht mein Fall, aber an diesen tagen weiß ich ganz genau warum ich letztes Jahr 300 Euro in eine Klimaanlage investiert habe.

Heute Abend haben wir es geschafft nach 3 tagen Power coding haben wir endlich das neue #Musik Tool fertiggestellt und eine Betaversion online stellen können. Diese Betaversion ist jetzt sogar ohne eine Änderung zum Livesystem geworden.

Soweit zu den News von #Musik. Des weiteren laufen jetzt alle Stämme Server auf der neuen Version 5.6 und ich muss sagen:

> Joar, läuft
>
> Und das sogar ziemlich gut.

Nach den letzten kleinen fixes in der Testwelt gab es eigentlich keine Größeren Probleme, außer das ich heute den Spielkern Kurzzeitig mit fehlenden Klammern tot gesetzt habe, und das auf den Livewelten :) Aber das war schnell behoben, außerdem will ich mal anmerken das es nicht meine Schuld war. Dazu ein Beispiel:

    if ($condition)
       do_important_things($with_this);
    else
       do_important_things($with_that);

Und ich so mutig wie ich nun mal bin hab da den Code den ich brauchte einfach mal dazwischen geklatscht und comittet. Ende vom Lied war leider, dass das Spiel auf unseren Servern nicht mehr laufen wollte. Wenn der Systenadmin reinkommt und fragt:

> “Soll der Demon nicht mehr laufen?
>
> Die dingens.php bricht immer mit ‘nem Fehler ab”

Und Ihr **GANZ **genau wisst ihr habt das vor 5 Minuten live gestellt dann ist das schon ein wenig blöd. Aber nach weiteren  3 Minuten waren dann die klammern ergänzt und alles war wieder gut.

Leider komme ich wegen der relativ stressigen Update zeit nicht zum Lesen, aber im Moment geht es eh “nur” um SOAP und XML-RPC und da hat der liebe Lars gesagt das ist eh alt RESTFUL ist das was du können willst. Leider kann Google mit solch vieldeutigen begriffen nur wenig anfangen. Aber ich behalte es einfach mal im Hinterkopf, hat wohl was mit JSON zu tun.

By the way: Mal sehen ob mir jemand n paar Fragen beantworten kann bzw. will:

1.  Wie kann ich herausfinden wie viele Leute den Blog hier via RSS abonniert haben?
2.  Zend, Cake oder Codeigniter?

So long…
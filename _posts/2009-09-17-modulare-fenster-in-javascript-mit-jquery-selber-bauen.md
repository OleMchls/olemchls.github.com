---
title: Modulare Fenster in JavaScript (mit jQuery) selber bauen
author: Ole Michaelis
layout: post
permalink: /2009/modulare-fenster-in-javascript-mit-jquery-selber-bauen/
dsq_thread_id:
  - 749064144
categories:
  - One Step
tags:
  - HTML
  - JavaScript
  - jQuery
---
# 

Nabend,

Heute will ich euch (wer auch immer das nun seien mag) einmal ein codesnippet aus dem X-Mailer zeigen. Es geht darum das alert fester, was Javascript ja von Haus aus beherrscht, in seinen Code so nach zubauen, das man das Design an die Seite anpassen kann. Die HTML Implementierung schenke ich mir an dieser stelle jetzt einmal. Dafür kommen wir direkt zum JavaScript teil. Weil der Name “*alert*” natürlich schon belegt ist habe ich “*msg_box*” genommen.

`function msg_box(msg_text) {
$('#overlay').show();
$('#msg_box').show();
$('#msg_box p').html(msg_text);
}`

`function close_msg_box() {
$('#msg_box p').text('');
$('#overlay').fadeOut('fast');
$('#msg_box').fadeOut('fast');
}`

Dann nun noch eine kleine Erklärung:

Die Funktion *msg_box* zeigt zuerst das overlay div an. Dieses überdeckt den ganzen Content der Page, das ist dafür gut um das **modulare **an dem Fenster nachzubilden. Also das die Page, solange das Fenster geöffnet ist nicht bedienbar zu machen. Danach wird das eigentliche Fenster eingeblendet (Die Fenster (-divs) sind alle schon im HTML Code mit *display:none* versehen). Dann wird noch die individuelle Massage die Ihr anzeigen wollt in das Fenster gefüllt. Das Fenster hat unten rechts dann noch einen Button der beim klick (*onclick*) die Funktion *close\_msg\_box* aufruft. Diese entfernt den Text aus dem HTML Code. Und blendet das *overlay *und die *box *wieder aus.

Einfach nicht? (fast schon billig)  – Aber so hat man die Möglichkeit das “*alert*” Fenter (mit CSS) seiner Seite anzupassen.

Das war’s auch wieder für heute, so long …


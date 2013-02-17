---
title: 'WTF des Tages! Heute: Mailserver'
author: Ole Michaelis
layout: post
dsq_thread_id:
  - 755876015
categories:
  - W T F ?! of the day
tags:
  - Debain
  - Mailserver
  - PHP
---

Und weil wir grad schon dabei sind und die Themen, Thematisch überhaupt nicht zusammen passen **und** weil ich grade noch eine Idee für eine neue Kategorie hatte, hier gleich noch ein Post.

Das WTF des Tages!  Heute: Mailserver bei 1Blu oder doch in PHP ?

Wie eben bereits erwähnt gab’s (quasi) heute den vServer, nachdem dann alles eingerichtet war. Fehlte mit noch der Mailserver, damit unter anderem WordPress aber auch später meine Scripte eMails versenden können. Also erstmal in die php.ini geschaut. Hier jetzt mal der original eintrag:

`[mail function]
; For Win32 only.
SMTP = localhost
smtp_port = 25
; For Win32 only.
;sendmail_from = me@example.com
; For Unix only.  You may supply arguments as well (default: "sendmail -t -i").
;sendmail_path =
; Force the addition of the specified parameters to be passed as extra parameters
; to the sendmail binary. These parameters will always replace the value of
; the 5th parameter to mail(), even in safe mode.
;mail.force_extra_parameters =`

Soweit so klar! Und das bei Debian 5 Lenny. Das ist also die vorgegebene config von 1Blu. An dieser stelle sei vielleicht einmal kurz angemerkt das ich sendmail noch nie benutzt habe und auch 0-Plan davon habe. Ich bin also mal davon ausgegangen das das wohl jetzt erstmal nicht funzt mit dem Mailversand. Also geschaut nachm Mailserver und wie man sowas einrichtet und und und… Dann am ende doch so genervt gewesen und es einfach mal mit der WordPress Installation getestet. Und ergebiss, ihr ahnt es. ES GEHT!

W  T  F  ?!

Ich habe nun wirklich keinen plan wieso und warum. Also noch schnell ein mail() Test zusammen geschrieben.

`
if(mail("You@yourprovider.com","Test E-Mail","Wenn das jetzt kalppt siehste den Text gleich nochmal im E-mail Postfach")){
   echo "Klappt";
}
else{
   echo "Klappt leider nicht";
}
?>`

Und natürlich auch das geht. Und niemand weiß warum. An dieser Stelle sei auch nochmal der bescheidenen Support von 1Blu gegrüßt, so wenig Ahnung hab ich auch schon lange nicht mehr erlebt.


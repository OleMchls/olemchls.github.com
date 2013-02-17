---
title: Speed up your Blog! Part 3
author: Ole Michaelis
layout: post
dsq_thread_id:
  - 746805822
categories:
  - One Step
  - Speed Up!
tags:
  - Apache
  - Apache Config
  - Blog
  - Linux
---

Moin und Wilkommen zum letzten Teil der Serie Speeed up your Blog!

Nachdem es letzte Woche um die Expire-Header ging, und davor auch um zipp’ed Content, will ich mich nun den Geschwindigkeitsverbesserungen im Code selbst widmen. Also weg von der Server-config ;)

**HTTP-requests minimieren / Javascript und CSS Dateien “Crunchen”**

Die letzten beiden Punkte möchte ich einfach mal zusammenfassen, denn grade wenn Ihr WordPress benutzt, gibt es dafür eine sehr einfache Lösung die quasi gar keiner weiteren Erklärung bedarf. Dennoch möchte ich zuerst einmal darauf eingehen warum dieser Punkt auch Performance Steigerung bringen kann. Denn Ein Browser schafft ca 5 Requests gleichzeitig, das ist also die Ideale anzahl an Request für euren Blog / eure Homepage. Wer das hinbekommt, bekommt ein Sternchen von mir, denn das ist nur sehr sehr schwer möglich! Alles was eure Page mehr an requests braucht, muss also nacheinander abgearbeitet werden. Das kostet Zeit und das nicht zu wenig.

Kommen wir zum nächsten Punkt, wenn ihr schon dabei seid eure CSS und JavaScript Files irgendwie zusammen zu schustern, dann bietet es sich i.d.R. auch IMMER an, diese gleich zu minimieren, oder auch “crunchen”. Dafür gibt es offene Projekte wie z.B. [Minify][2], das auf GoogleCode gehosted wird. Oder aber man implementiert es gleich selbst, das ist im übrigen auch das was ich getan habe, nicht für diesen Blog aber für “Die Stämme”. Allerdings sollte man sich zum “crunchen” der dateien an fertigen Biblitheken bedienen, denn hier macht es wenig sinn, das Rad neu zu erfinden. Ich bin am ende für JavaScript bei [JSmin][3] gelandet, und für CSS beim [CSS.Kompressor von Minify][4].

 [2]: http://code.google.com/p/minify/ "Minify"
 [3]: www.crockford.com/javascript/jsmin.html "JSmin"
 [4]: http://code.google.com/p/minify/source/browse/trunk/min/lib/Minify/CSS/Compressor.php "CSS Kompressor von Minify"

Hier gibt es einspar potenzial, wenn Ihr z.B. die CSS datein soweit aufsplittet, das jede unterseite eine eigene CSS datei hat diese sucht ihr dann beim aufrug zusammen, fasst sie auch in eine datei zusammen, dann nurnoch mit einem Kompressor drüber und voila, schon hat man die perfekte CSS-Datei, diese kann man dann noch Weg-Cachen, denn das Crunchen, bruacht schon eine menge CPU Zeit.

Solltet Ihr WordPress benutzten, ist die Lösung viel viel einfacher: Die Lösung heißt [CSS-JS-Booster][5], diesen einfach wie jedes andere WP-plugin auch installieren und es nimmt euch genau die von mir eben beschriebenen Schritte ab.

 [5]: http://github.com/Schepp/CSS-JS-Booster "CSS-JS-Booster"

Klasse! Das soll es jetzt auch erst einmal gewesen sein, vielleicht konnte ich dem ein oder enderem etwas neues zeigen, über Feedback würde ich mich diesmal sogar noch mehr freuen als sonst ;)

Vielen dank geht an dieser Stelle an Lars ;)


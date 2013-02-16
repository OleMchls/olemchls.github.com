---
title: Speed up your Blog! Part 1
author: Ole Michaelis
layout: post
permalink: /2010/speed-up-your-blog-part-1/
dsq_thread_id:
  - 746805852
categories:
  - One Step
  - Speed Up!
tags:
  - Apache
  - Apache Config
  - Blog
  - Linux
---

Moinsen,

Heute mal wieder etwas nützliches, ich habe grade mal ein wenig an der Performance von meinem Blog gedreht, eigendlich ist es garnicht so schwer. Und wie so oft die besten ergebnisse erreicht man mit den kleinen Änderungen

*   Content gezipp’t ausliefern
*   Die expire header richtig setzten
*   HTTP-requests minimieren
*   Javascript und CSS datein “crunchen”

So nun will ich noch erklären wie man diese änderungen für seinen Apache Webserver richtig einstellt. Ich habe hier folgende vorraussetzungen:

Einen Debian Etch vServer, Apache Webserver, PHP, MySQL usw… also das klassische LAMP-Setting.

Damit der Artikel jetzt nicht eeeeeeeeeeeeeeeeewig lang wird, gibt es zu jedem der Punkte oben jede Woche einen neuen Artiekel!

Fangen wir also an!

**Content gezipp’t ausliefern**

Die absolut beste möglichkeit ein riesen Stück performance zu gewinnen! Einfach die folgende config um diese Zeiler erweitern

```bash
/etc/apache2/mods-enabled/deflate.conf
```

```bash
AddOutputFilterByType DEFLATE text/html
AddOutputFilterByType DEFLATE text/plain
AddOutputFilterByType DEFLATE text/xml
AddOutputFilterByType DEFLATE text/css
AddOutputFilterByType DEFLATE text/javascript
AddOutputFilterByType DEFLATE application/x-javascript
AddOutputFilterByType DEFLATE application/javascript
AddOutputFilterByType DEFLATE image/png
AddOutputFilterByType DEFLATE image/gif
AddOutputFilterByType DEFLATE image/jpg
AddOutputFilterByType DEFLATE image/jpeg
```

Die Datei kann natürlich um jeden beliebigen MIME-Type noch erweitert werden. So das war es auch schon, jetzt noch einmal den Apache neustarten und ihr werdet es sehen, wenn ihr jetzt mal eure Seite betrachtet, es wird eine menge gebracht haben. ;) Versprochen!
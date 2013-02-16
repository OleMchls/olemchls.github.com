---
title: Speed up your Blog! Part 2
author: Ole Michaelis
layout: post
permalink: /2010/speed-up-your-blog-part-2/
dsq_thread_id:
  - 843363584
categories:
  - One Step
  - Speed Up!
tags:
  - Apache
  - Apache Config
  - Blog
  - Linux
---
# 

Moin Moin,

Nachdem wir uns letzte Woche um den gezippten Content gekümmert haben soll es heute weiter gehen mit den Expire-Header

**Die expire header richtig setzten**

Hier wird es jetzt schon etwas Tricky, denn sobald ihr Content mit Expire-Headern ausliefert, fordert der Browser die Daten gar nicht erneut an, wenn die Expire Zeit noch nicht abgelaufen ist. Also werden Änderungen nicht an den Client übertragen. Jetzt gibt es mehrere Möglichkeiten, entweder ihr hängt an jede Datei einfach einen weiteren GET-Parameter, der die sog. “mtime” (maketime) als UNIX-Timestamp enthält, oder aber ihr wisst ihr habt sowieso nicht sooo viel Bewegung in eurem Pagequellcode, wie es eigentlich bei fast jedem 0-8-15 WordPress  Blog sein sollte. Ich habe mich für die 2. Möglichkeit entschieden, allerdings setze ich dann die ExpireHeader nicht soweit in die Zukunft.

Also los geht es,

`/etc/apache2/mods-enabled/expires.conf`

bei mir gab es diese Datei anfangs gar nicht, also einfach anlegen.  
`
ExpiresActive on
####ExpiresDefault "access plus 2 months"
ExpiresByType image/x-icon "access plus 1 month"
ExpiresByType image/png "access plus 1 month"
ExpiresByType image/jpg "access plus 1 month"
ExpiresByType image/gif "access plus 1 month"
ExpiresByType image/jpeg "access plus 1 month"
ExpiresByType application/pdf "access plus 1 month"
ExpiresByType application/javascript "access plus 1 month"
ExpiresByType audio/x-wav "access plus 1 month"
ExpiresByType audio/mpeg "access plus 1 month"
ExpiresByType video/mpeg "access plus 1 month"
ExpiresByType video/mp4 "access plus 1 month"
ExpiresByType video/quicktime "access plus 1 month"
ExpiresByType video/x-ms-wmv "access plus 1 month"
ExpiresByType application/x-shockwave-flash "access 1 month"
ExpiresByType text/css "access plus 1 hour"
ExpiresByType text/javascript "access plus 1 hour"
`

Ich denke die datei ist quasi selbsterklärend. Nächste Woche geht es dann weiter mit HTTP-Requests und Content-Compressors ![;)][1] 

 [1]: http://blog.codestars.eu/wp-includes/images/smilies/icon_wink.gif


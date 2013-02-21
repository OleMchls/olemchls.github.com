---
title: Themes for Netbeans
author: Ole Michaelis
layout: post
categories:
  - Tools
tags:
  - IDE
  - look and feel
  - netbeans
  - themes
---

Hey folks,

It’s weekend, so there’s time for own projects and if you do like me, you already programmed the first five days before weekend. So its time for a variety!

While I clicked through the NetBeans wiki *(Do you know that NetBeans 7 will come with git support?)*, I discovered that netbeans can also handle some kind like themes, called Look and Feel in Java. And you can easily switch between a few themes without any download anything, all the look and feel’s came with the JDK. I tried a few, but most of the things I downloaded are broken in any kind. So I will show you the inbuild ones. take a look!

[![GTK - NetBeans IDE 6.9.1][1]][1]
GTK - NetBeans IDE 6.9.1

[![Metal - NetBeans IDE 6.9.1][2]][2]
Metal - NetBeans IDE 6.9.1

[![Nimbus - NetBeans IDE 6.9.1][3]][3]
Nimbus - NetBeans IDE 6.9.1

And you can also download a﻿﻿ variety of others.

 [1]: //assets/uploads/2011/01/playground-NetBeans-IDE-6.9.1_003.png
 [2]: //assets/uploads/2011/01/playground-NetBeans-IDE-6.9.1_004.png
 [3]: //assets/uploads/2011/01/playground-NetBeans-IDE-6.9.1_006.png

You can try these themes with a single parameter on you netbeans call, like:

```bash
$ /bin/sh “path/to/netbeans/bin/netbeans” –laf com.sun.java.swing.plaf.nimbus.NimbusLookAndFeel
```

You want to keep these theme? Just set it in your *netbeans.conf*, its located in your NetBeans etc folder. Just add the –laf parameter to ﻿*netbeans\_default\_options*

If you want to see more screens or need more help with the config. Take a look at [The NetBeansPHP Blog][4], they put a lot more screens on their page. I think I will go on with Nimbus, or Metal, don’t really know:)

 [4]: http://blogs.sun.com/netbeansphp/entry/how_to_change_look_and

Happy coding!


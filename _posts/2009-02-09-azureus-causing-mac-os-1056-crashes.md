---
layout: post
title: Azureus Causing Mac Os 10.5.6 crashes
tags: []
---

After trying a bunch of stuff, I found out that Azureus was causing
kernel panics when I was connected on airport, switching to uTorrent fix
it.

Heres the kernel panic, for people googling this:

<blockquote>
Sun Feb Â 8 20:09:21 2009

panic(cpu 0 caller 0x002232C6): “rtunref: bad refcnt 0 for
rt=0x132fe690\\n”@/SourceCache/xnu/xnu-1228.9.59/bsd/net/route.c:460

Backtrace (CPU 0), Frame : Return Address (4 potential args on stack)

0x5b467dc8 : 0x12b4f3 (0x45b13c 0x5b467dfc 0x1335e4 0x0)Â 

0x5b467e18 : 0x2232c6 (0x473df8 0x0 0x132fe690 0x1a336f)Â 

0x5b467e38 : 0x2237ba (0x132fe690 0x1 0x0 0x0)Â 

0x5b467e68 : 0x224a66 (0x132fe690 0x2 0x5b467e98 0x13b3ba4c)Â 

0x5b467e88 : 0x273cfd (0x132fe690 0xffff 0x1 0x3aa793)Â 

0x5b467eb8 : 0x24adb9 (0x13b3ba4c 0x6d76080 0xde 0x1a0420)Â 

0x5b467f18 : 0x24ccba (0x13b3bb2c 0x2 0x1 0x24eb3f)Â 

0x5b467f58 : 0x39befb (0x6d763a0 0x23ac6252 0x5b467f78 0x1a336f)Â 

0x5b467f78 : 0x13eed2 (0x0 0x0 0x0 0xbfffedc0)Â 

0x5b467fc8 : 0x1a017c (0x0 0x0 0x1a30b5 0x74ea2e8)Â 

Backtrace terminated-invalid frame pointer 0

Â 

BSD process name corresponding to current thread: kernel\_task

Â 

Mac OS version:

9G55

Â 

Kernel version:

Darwin Kernel Version 9.6.0: Mon Nov 24 17:37:00 PST 2008;
root:xnu-1228.9.59~1/RELEASE\_I386

System model name: MacBookPro3,1 (Mac-F4238BC8)

</blockquote>

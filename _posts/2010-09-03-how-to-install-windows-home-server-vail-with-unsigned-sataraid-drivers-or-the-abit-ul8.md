---
layout: post
title: How to install Windows Home Server Vail with unsigned SATA/RAID drivers, or
  The Abit UL8.
tags: []
---

<ol>
<li>
Boot off of install media, as usual.

</li>
<li>
Hit Shift-F10 to open a command prompt.

</li>
<li>
It should open in X:\\sources, CD into X:\\sources\\recovery.

</li>
<li>
run RecEnv.exe

</li>
<li>
Hit next on the Select your keyboard layout window, then click load
drivers.

</li>
<li>
Browse for and load your unsupported SATA drivers.

</li>
<li>
Leave the recovery window open, and continue with installation, your
unsupported hard drives should now appear.

</li>
</ol>
**EDIT: This should also work for Windows 7 and possibly 8 (Haven’t
tried). You may need to boot with signature checking disabled.**

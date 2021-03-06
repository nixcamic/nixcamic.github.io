---
layout: post
title: Dead Mushkin IO Drive
tags: []
---

I was recently given a dead 256GB Mushkin IO drive by a friend. Wouldn’t
show up at all on boot, Mushkin firmware update utilities wouldn’t find
it etc. Digging around I found out that it’s based on an Indilinx
Barefoot controller and Samsung Flash memory, and that setting the
jumper next to the SATA connector puts it into factory “technological”
mode. I also managed to find a recent copy of the Indilinx MPTool (used
for reprogramming/upgrading flash drives) thanks to SuperTalent. I’m
putting everything you need to know together here to save y’all some
trouble.

While this guide was tested on a Mushkin IO drive, it should work on any
Indilinx Barefoot based SSD. Let me know your results in the comments.
Note that you must have a drive that shows up as a “Yatapdong Barefoot
ROM” when the factory diagnostic or “technological mode” jumper (right
next to the SATA connector) is set or this most likely wont work for
you.

1.  Download the Indilinx MPTool from
    [Here](http://www.supertalent.com/home/forum/viewtopic.php?f=74&t=10867)
    or
    [Here](https://mega.co.nz/#!d0hCjQrS!FReKTyK_P9nJKCvsHuBzii3Zb6V6zsc_ijV2MFJvBoM)
    and install it.
2.  Set the factory diagnostic or “technological mode” jumper (right
    next to the SATA connector).
3.  Set your SATA controller to IDE or Compatibly mode.
4.  Boot into Windows and open up MPTool, if you’re running Vista, 7 or
    8 you need to run it as an administrator.
5.  Your drive should show up in the list of drives on the lower half,
    make sure it’s selected.
6.  Set the Serial Number to random, you can change the Model Number if
    you don’t want it to show up as a SuperTalent SSD, doesn’t matter.
7.  Go to the Flash tab and check Auto Detection.
8.  Hit the Start button. It should pop up a black console window and
    run for a few minutes, spitting out a bunch of text. Sometimes it
    will fail right away (within the first 10-20 seconds), just hit
    start again and it should run.
9.  It will tell you to remove the jumper. Remove the jumper, without
    disconnecting the drive.
10. It’ll sit there for a few more minutes, then the console window
    should disappear and it should say FINISH next to your drive.
    Congratulations, your drive should be working now and Windows should
    start detecting it. As a bonus, your drive is also running the
    newest firmware release for the Indilinx controller.

After doing this you won’t be able to upgrade or flash your drive using
any of the Mushkin (or any other manufacturer) tools, only MPTool.
However, since you’re at the last firmware version to be released for
this controller, thats probably not a problem.

---
layout: post
title: Fixing a Galaxy S with dead internal storage.
tags: []
---

*If you just want the image and instructions on how to fix your phone,
skip down to the Downloading/Installing section of the post.*

How to rebuild a Samsung Galaxy S zImage
========================================

A friend of mine asked if I could fix his Galaxy S for him. After
starting it up and poking around I discovered that the build in flash
storage was dead. Since that storage shows up to the system as a SD
card, and theres a space for an external SD card, I figured I’d just
change some stuff in fstab and be done with it.

It’s a UNIX system, I know this. Right?

Not right.

Unfortunately Android doesn’t store it’s mounts in fstab. No, they’re
hardcoded into the init scripts. So change the init scripts and be done
with it.

Nope.

The init scripts are stored in the initrd, which is tacked onto the end
of the kernel image in a proprietary Samsungy way. So no standard
Android tools will extract it so I can modify it. Of course…

But there is still hope! Fortunately someone has already figured
everything out and posted their tools online
[here.](https://github.com/project-voodoo/kernel_repack_utils)

Using this and the cross compiler found
[here](http://www.codesourcery.com/sgpp/lite/arm/portal/package5385/public/arm-none-linux-gnueabi/arm-2009q3-67-arm-none-linux-gnueabi.bin)
(I had to modify the kernel repack utils to use this since it’s a
different version than they were built for. If you’re getting this far
that shouldn’t be a problem for you.) I was able to extract the initrd,
modify it to change the device paths, and rebuild the kernel image. Once
I had the rebuilt kernel image I flashed it to the phone, as I’ll go
into below:

Downloading/installing the kernel
=================================

You’ll need a SD card with two MBR FAT32 partitions, the first one
should fill most of the card, you can use it for general storage as you
would a normal SD card, the second should be about 2-4GB big for the
Android /data partition.

I uploaded the custom image I made so that nobody else has to go through
this pain.

[Download](https://mega.co.nz/#!R4hgTA4S!B6GZklu8m7GXxUQ6juU4DnXzd3NWjFWlg4INWplYoas)  
[Mirror](http://terafile.co/89b79d05a435/zImage.new)

This kernel is for the XXJW4 firmwares, if you aren’t already running
one you need to be on it for it to work. The exact firmware I’m running
is available
[here](http://samsung-updates.com/details/17571/Galaxy_S/GT-I9000/XEU/I9000XXJW4.html)
“(mirror)”:http://terafile.co/268887f61345/XEU-I9000XXJW4-20120405163836.zip
but any XXJW4 firmware should work. Google can help you find/install
one.

I installed it with [Heimdall](http://glassechidna.com.au/heimdall/)
with the following command:

    heimdall flash --KERNEL zImage.new

From within the directory with the zImage.new file you downloaded above.
You need to be in download mode (once again, google is your friend) for
this obviously.

Once you reboot, your phone should come up like new, but now all storage
is on the external SD card. Obviously, this card needs to remain in the
phone at all times.

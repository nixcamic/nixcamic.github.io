---
layout: post
title: Armv6 support possible in Xcode 4.4.1
tags: []
---

Supposedly Xcode 4.4.1 drops all support for armv6 processors. It
doesn’t appear to be that way since you can still compile for armv6 by
adding it as a target and the app will run on armv6 devices. However
currently running the app directly from Xcode causes my iPhone to
reboot. I think it may be because of my gimpy (4.1 redd00r) firmware,
I’m gonna reflash when I get home and try again.

Edit: Ok, running stock 4.2.1 everything works exactly the same as it
did in all previous versions of Xcode 4. You just need to add armv6 as a
target, use GDB instead of LLVM for debugging and set the deployment
target to iOS 4.2 (For iPhone 3g, 3.1.3 for 2g). Armv6 works just
peachy, it’s just not the default option anymore.

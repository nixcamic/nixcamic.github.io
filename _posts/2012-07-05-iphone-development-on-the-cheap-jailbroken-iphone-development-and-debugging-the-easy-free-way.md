---
layout: post
title: iPhone Development on the Cheap (Jailbroken iPhone development and debugging
  the easy free way)
tags: []
---

So you want to build jailbroken iOS apps, but are to poor or cheap to
shell out $100 to Apple? No problem at all. Maybe you’ve tried guides
like [this
one](http://www.alexwhittemore.com/developing-jailbroken-iphone-ios-401/)
or [this](http://iphonedevwiki.net/index.php/Xcode) .

Those guides are great and I build off of them for mine. I’ve used both
methods with older versions of Xcode with great success. But neither
would work for me in newer versions of Xcode. Fortunately I found
another way. An easier way. A way with debugging support. A better way
:)

A way that works in Xcode 4.3.2 and possibly newer:

1. Obviously we’re gonna need a computer with Xcode and a Jailbroken
iDevice.

2. On the computer you need to create a code signing certificate. Open
Keychain Access, click the Keychain Access menu and open the Certificate
Assistant -&gt; Create a Certificate. Create a “Self Signed Root” “Code
Signing” certificate named “iPhone Developer”.

3. On that jailbroken iDevice you’re going to need to install AppSync.

Installing AppSync is simple:  
Add the source http://cydia.hackulo.us to your Cydia sources. Cydia will
give you a warning, because pirates use AppSync. You aren’t going to be
doing that I hope, ignore the warning.

Install AppSync for whatever iOS version you run from Cydia.

4. Open
/Applications/Xcode.app/Contents/Developer/Platforms/iPhoneOS.platform/Info.plist  
in whatever editor you use and replace all occurrences of
XCiPhoneOSCodeSignContext with XCCodeSignContext.

5. In your project in Xcode go to your Target settings -&gt; Summary and
scroll to the bottom. Enable Entitlements. Xcode should automatically
create and Entitlements file. Add a new row named “get-task-allow” of
the boolean type with a value of YES. Make sure this row is all the way
left and *not* part of the keychain-access-groups array. You’ll have to
do this on every project, but it’s not much.

6. Everything should be working now. You may need to use GDB as your
debugger to get debugging working, this can be done in Project -&gt;
Edit Scheme.

I’m writing most of this from memory so comment if you have any problems
along the way. Also I’ve only been able to test on iOS 3.1.3 devices so
far, on account of that being all I have available.

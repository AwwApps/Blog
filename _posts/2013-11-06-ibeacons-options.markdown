---
layout: post
title: "iBeacons, current options"
date: 2013-11-14 16:32
comments: true
author: Bernd
published: true
categories:
- Lab
- iBeacon
---

![iBeacon Devices]({{ site.url }}/images/post_ibeacon.svg)

Welcome to our new 'area of intense interest'. iBeacons. Introduced with iOS 7, this Bluetooth based standard enables a new level of location and micro-location awareness for  apps. Currently we do some early experimentation to get a grip of what can be done and getting a feeling for its limitations.

Although iBeacon as a standard is pretty young, it's easy to get started. You might be surprised how many devices you already own that can easily be turned into iBeacon emitters.

This is of special interest for those of us who like starting to build apps and those who test an iBeacon enabled app that some nice people <a href="#peoplemakingapps">¹</a> built for them.

### Mac <span class="marker-thin">OS X</span>

The option to turn your Mac into a iBeacon isn't a system setting just yet. Count the days … . In the meanwhile Matthew Robinson wrote a simple **Beacon Emitter** app. You can set all relevant beacon attributes, like UUID, major and minor ID to broadcast. You might not want to have this running all day but it's great for testing. Read about the Emitter and its code on his [blog](http://www.blendedcocoa.com/blog/2013/11/02/mavericks-as-an-ibeacon/). Thanks Matthew!

→ Requirements: [Source code](https://github.com/mttrb/BeaconOSX), Xcode to build the app.

### iPad, iPhone or iPod touch <span class="marker-thin">iOS</span>

**Beacon Emitter** is a simple iBeacon emitter app for iOS. It's based on Apples iBeacon example project "Air Locate" from this year's WWDC. It's a great starting point for creating your own iBeacon enabled app. In order to work the Beacon Emitter app needs to be active and in the foreground.

→ Requirements: [Source Code on Github](https://github.com/ohrobot/BeaconEmitter), Xcode to build the app, a device running iOS7.

### Raspberry Pi + Bluetooth USB Dongle <span class="marker-thin">Linux</span>

If you are still looking for a reason to get a Raspberry Pi, this might be a good one. It's probably the most inexpensive – yet time consuming – way to get an _always-on_ beacon running.

The Pi is a fun tiny machine. However there are some flaws to be aware of. The OS (Raspbian) runs from an SD Card, which implies a quite limited life-time. When you unplug the Pi a few times without shutting it down from the command line first, file system corruption is very likely. In that case your Raspberry Pi won't boot anymore. You need to reformat and start over.

Power. First we were excited seeing the Pi powered by the minimalism of a USB jack only. What's the point of those bulky external power bricks, anyhow. Well, no so fast, please. It turns out that the power from USB just isn't stable enough for solid constant use. If you connect any additional USB dongles like Bluetooth, you will run into power fluctuation causing instabilities or random crashes. We ended up using an externally powered USB hub for those peripheral devices making it much less compact as we had wished for, but much more stable in the end.

And ... as with all Linux hardware you'll have this fun and nerve wracking buying experience of finding compatible hardware based on chipsets, rumors spread in forums and wiki pages. Be ready to dive in. This one worked for us: [Plugable USB-BT4LE](http://plugable.com/products/usb-bt4le)

→ Requirements: Raspberry Pi (A or B Model), Bluetooth USB Dongle, [Script](http://developer.radiusnetworks.com/2013/10/09/how-to-make-an-ibeacon-out-of-a-raspberry-pi.html)

### Estimote <span class="marker-thin">Embedded</span>

While you could consider the other options as too hacky for constant use, the Estimote isn't in that same category. It's a fully integrated and dedicated beacon. It's a well designed product with a clear focus and finally, low energy consumption. The level of integration comes with some compromises regarding the control you have over its inner workings. In contrast to the other options you cannot set the UUIDs manually. That's a limitation as Apple's recommendation is in deed to use one UUID for all devices of one use case. Also the Estimote doesn't come with an official way to replace its battery.

> If the battery is running out of power, it will let you know. You don't have to change it, because in two years sensors will be more advanced and you can get a new version. If you want you can always open it. – _[Estimote, FAQ](http://estimote.com)_

Fair enough. But from a sustainability point of view this feels a bit disheartening. That being said Estimotes might still be the best stand alone beacons you can currently get. It's a very smart move from Estimote to make their beacon small yet very appealing and recognizable. It's an inspiring little thing. Kudos.

In addition to the beacons there is also a Virtual Beacon App that shows potential beacon use cases plus functions as emitter, monitoring and setup tool for Estimote beacons.

→ Requirements: Estimote Dev Kit, [Estimote Virtual Beacon App](https://itunes.apple.com/us/app/estimote-virtual-beacon/id686915066)

### Overview

| 					|  Mac	 		| iOS Device 	| Raspberry Pi 	| Estimote
|					| ------------ 	|------------ 	| ----------- 	|-----------
|**Battery Run Time**	| Hours			|	Hours		|	Minutes		|	Months
|**Custom UUID**		| Yes			|	Yes			| Yes			|	No
|**Price**				| min. 629€	 	|	min. 240€	| min. 50€		|	134€ (3 beacons)



While there's no shortage of options for testing, having a beacon for constant usage is a whole different story. We are still evaluating all available beacon options. If you have experiences with other alternatives, please let us know.

<p id="peoplemakingapps">¹ *wink* ;)</p>

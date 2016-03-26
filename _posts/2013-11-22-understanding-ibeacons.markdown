---
layout: post
title: "Understanding iBeacons"
date: 2013-11-22 18:24
comments: true
author: Bernd
categories:
- Lab
- iBeacon
---

With the introduction of iBeacons a new level of spacial awareness comes to iOS. It's a meaningful extension to CoreLocation's underlying technologies like GPS and Wifi Triangulation. iBeacons provide centimeter grade accuracy and even extend location services to indoors.

![iBeacon Precision]({{ site.url }}/images/post_understanding-ibeacons_tracking_precision.svg)

<div class="caption">Data for GPS<a href="#rangingfootnote">¹</a> Wifi<a href="#rangingfootnote">²</a> iBeacon<a href="#rangingfootnote">³</a> accuracy</div>

This however comes with one caveat. Unlike the existing location services you need to build upon your own infrastructure of iBeacons. As long as no objects and furniture come with emitters built-in you can do this by using dedicated iBeacons. Fortunately iBeacons are based on a simple open standard allowing them to be low energy and relatively inexpensive. This is possible because an iBeacon does not receive or compute any data. It solely broadcasts its identity. Over and over. All processing is done on the side of an app set up to recognize specific iBeacons.

### Data

Besides its **identity** the only variable data you can get from an iBeacon is its measured **signal strength**. iOS turns this into a surprisingly accurate estimate of proximity in meters. Expect about 0.1 m or less in terms of precision.

But no magic involved. Walls will of course damp the signals and distort the estimated proximity significantly. But at times this can also come handy, allowing for easier separation of ranged iBeacons by room, especially as there's no sense of direction tied to the signal.

### Scan

If Bluetooth is enabled, iOS constantly monitors all possible iBeacon signals around. About once every second you get updated scanning results. They are filtered by the iBeacons' primary identifier, the **UUID** . UUIDs look like this: _187FA1EC-2B52-4E33-9478-A97BDB29E1E6_.

![iBeacon Ranging]({{ site.url }}/images/post_understanding-ibeacon_ranging.svg)

Ideally all your iBeacons have the same UUID. It is possible to have your app listen to multiple UUIDs but the amount is limited and you also might save a tiny bit of battery life reducing the list of monitored UUIDs.

### Identify

As the UUID is most likely shared between all your iBeacons, you need additional identifiers to differentiate individual ones: The numerical **Major ID** and **Minor ID** are here to help. A meaningful system would be e.g. to use a Major ID for each room/location and a Minor ID for the specific placement spot of your iBeacon. This is also what Apple recommends.

<div style="border:1px solid lightgray; border-radius:5px; text-align:center; padding-top: 15px; padding-bottom: 15px;"> All monitored iBeacons <strong>UUID</strong> → Room/location <strong>Major ID</strong> → Spot <strong>Minor ID</strong> </div>

However also keep in mind that there are totally different use cases where the beacon is attached to a moving object like a train, a bike or a bagpack. So it's really up to you to come up with a 3 tier identification system that fits your need best. Granted of course the iBeacons you use let you do these choices – and they really should.

### 101% secure ...

First signs of a controversial discussion around this level of control and potential security issues by imitating existing iBeacons IDs turned up recenly on [Estimote's SDK Github page](https://github.com/Estimote/iOS-SDK/issues/9#issuecomment-28444439).

You should definitely be aware of the fact that every iBeacon can be cloned by _simply_ knowing it's UUID. Major and Minor ID can then be tracked down. Therefore you should rather see iBeacons as simple location based app triggers than as potential integral part of some super secure personal identification setup. Tell them, we warned you.

### Integrate

And here comes the fun part. Your app can tell iOS to wake up in the background on **entering** or **exiting** the range of an iBeacon or when the **lock screen** is shown. The app then will be granted a tiny bit of background processing you can use e.g. for logging or throwing a local notification, providing an iBeacon-aware path back into your app.

![iBeacon Notifications]({{ site.url }}/images/post_understanding-ibeacons_tracking_notification.svg)

While this might sound quite limiting it actually is a nice compromise between making iOS and the user aware of a potential action but without getting overly invasive.

Alright. So we now know something about the nature of iBeacons as well as [available options](/blog/2013/11/14/ibeacons-options/) to get them running. High time to think of some good use cases and start creating!

Data, Accuracy for <span id="rangingfootnote">¹</span> [GPS](http://www.gps.gov/systems/gps/performance/accuracy/) <span id="rangingfootnote">²</span> [Wifi Triangulation](http://googlexxl.blogspot.de/2008/01/la-triangulation-wifi-avec-skyhook.html) <span id="rangingfootnote">³</span> iBeacon, simple testing experience

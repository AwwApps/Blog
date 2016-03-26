---
layout: post
title: "Manual iBeacon entry to be removed"
date: 2014-05-20 02:11
comments: true
categories:
- Launch Here
- Travel Radar
- iBeacon
- Support
---

![Open Beacon Credentials]({{ site.url }}/images/post_discontinued_manual_ibeacon_entry.svg)

<span class="marker">Support note</span> With the upcoming updates of our iBeacon apps [Launch Here](http://launchhere.awwapps.com) and [Travel Radar](http://travelradar.awwapps.com) we will remove the option to manually add and edit iBeacon credentials (UUIDs, Major ID, Minor ID). This is not our choice. We do this to keep the apps in the App Store.

We'll do our best to come up with other options to add your iBeacons – better options.

1. With our [latest update](/blog/2014/04/27/launch-here-1-2/) of Launch Here we already added basic **auto-detection** working with some iBeacons. We will improve on this and **extend support to more iBeacon vendors**. If your iBeacon doesn't get recognized please let us know by sharing its UUID with us  [here](https://docs.google.com/forms/d/1dA0flF9OYeAeGSQUF9yWp4KS3v62TnZGGBZ1tnsiSlo/viewform?usp=send_form). That would help us (and you) a lot. [Here](/blog/2014/06/18/supported-beacons/) are the iBeacon we currently support for auto-detection. Please note that a general scanning of all iBeacons around is not possible on iOS. We rely on your input to cover all commonly used iBeacons.

2. In addition we will **create a new unique set of IDs** for use with your iBeacons. Besides auto-detection this will unlock another feature you will love – predefined beacon names. More details on this will follow in a separate [announcement](/blog/2014/05/29/open-ibeacon-credentials/).

### Important

This change will likely lead to loosing support for some iBeacons which are not in our list of known vendors – especially for those that do not support setting a custom UUID. As most iBeacons still come as dev kits, you will most likely be able to do the necessary update. If not, please <a href="mailto:support@awwapps.com?subject=iBeacon%20Support">let us know</a>.

### Opinion

To clarify, we have full understanding for this newly enforced policy. iBeacon credentials really aren’t something that should be exposed to casual users. But to be honest with you we would have liked to keep the manual entry around just in case you need it. Unfortunately this is not an option.

We are convinced that going forward as harsh as this step may appear now will lead to a much better user experience. It will open up casual iBeacon applications to more people, especially those who are less tech savvy.

The app updates bringing this change are not ready to ship quite yet. But this is a significant change, so we wanted to give you this notice upfront. If you have any questions or additional ideas, please let us know. We always appreciate your feedback a lot.

We understand that this update will be a bumpy one for some users. We are very sorry for that.

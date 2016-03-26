---
layout: post
title: "Casual iBeacons"
date: 2014-03-19 20:29
published: true
comments: true
author: Bernd
categories:
- iBeacon
---

![Casual iBeacons]({{ site.url }}/images/post_casual_ibeacons.svg)

Since releasing [Placed](http://placed.awwapps.com "Placed") and [Travel Radar](http://travelradar.awwapps.com "Travel Radar") there are some questions we get asked a lot:

> Which iBeacon do you recommend?

We don't have a good answer to this. We *just build apps* and we have no direct affiliation with any iBeacon manufacturer. We don't use vendor specific code or frameworks to handle iBeacon signals. Our apps communicate with iBeacons solely by the standards defined by Apple. So, we really do recommend any kind of iBeacon. But wait …

> Why is it so hard to find iBeacons for casual use at home?

There are in deed a lot of iBeacons already available. However most of them are developer kits targeting retail environments and large deployments.

And here's the shocking truth: From our perspective iBeacons are not even conceived being used as separate consumer products. At least no at the moment.

Their only purpose is to **make specific apps be aware of specific places or things**. In fact as a user you don't even need to know that such a thing as an "iBeacon" exists. All you do is install an app that happens to act in smart context-sensitive ways – at the right spot, at the right time. No setup process or manual linking required. iBeacons? An implementation detail. Rainbows.

Going forward the most appealing cases for iBeacons can be made being integrated in existing products. Appliances, computers, furniture, Apple TVs, etc. - basically all *things* whose usage can be enhanced or accompanied by companion apps are great potential hosts for iBeacon emitters. Use cases and applications will drive iBeacon deployments not vice versa.

Apps like ours working across different iBeacons are outside of this mainstream scope. Although we'd like to stress that our apps work across iBeacon vendors this always will be to the detriment of a manual linking process between apps and iBeacons. And if you ever pasted a long UUID you know that this really feels like something that is not supposed to be done by *normal users*. Therefore if it really is for pure casual use, we cannot wholeheartedly recommend getting iBeacons just yet … at the moment an iBeacon really is a gadget that doesn't want to be one.

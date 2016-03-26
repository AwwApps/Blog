---
layout: post
title: "iBeacon - Technically"
date: 2013-11-10 19:20
comments: true
author: Bernd
categories:
published: false
---

### Technically

The core of the technological side of iBeacons is simple. One way. All an iBeacon really does is to broadcast its identifier. proximityUUID as well as a major and minor numeric value. If you setup Beacons you are supposed to use the same UUID for all beacons for one use case  and add individual major/minor values for further grouping and differentiation.

It's because you register this UUID as a region to be searched for on iOS. Visibilty is limited to those specific devices. I guess + battery + not more filtering

You see, no reason to not get started wiring up your appartment with a couple of beacons now.

To get building or test an app that some great studio built for you ;) you first need a beacon.

UUID Controversy

You need to rebuild if you want to add new UUIDs to scan

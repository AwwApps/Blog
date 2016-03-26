---
layout: post
title: "Open Beacon Credentials"
date: 2014-05-29 18:41
comments: true
published: true
categories:
- iBeacon
- Support
---

![Open Beacon Credentials]({{ site.url }}/images/post_open_beacon_credentials.svg)

Introducing a shared iBeacon identifier scheme for common personal use cases.

We were looking for a solution to enable **auto-detect** and **automatic naming** support for iBeacons on iOS that works **across different apps** and **beacon vendors** and found … nothing. So we came up with our own solution: **[Open Beacon Credentials](https://github.com/AwwApps/Open-Beacon-Credentials)**, a simple structured set of shared iBeacon credentials enabling one tap linking processes and covering the most common areas of personal iBeacon use.

Open iBeacon Credentials are meant to be used in isolated home environments and personal contexts. They are especially useful for apps that allow users to link their own iBeacons. Open Beacon Credentials provide a clear guidance on how to configure your iBeacon to make this connection work well.

We would love to see this scheme being adapted by other apps or even iBeacon vendors, too.

### Benefits

After setting up your iBeacon according to our UUID, Major/Minor ID scheme as a user you get the following features.

* **Auto-Detection** for iBeacons across different vendors and across different apps. No more exposure of UUIDs, Major/Minor IDs. This feature is based on using a shared UUID.
* **Auto-Naming** allows the assignment of a preset name to your iBeacons. No more need to enter a beacon name/location manually. This is based on using specific Major ID and Minor ID combinations following our scheme.

### Getting started

To setup your iBeacon using Open Beacon Credentials, all you need to do is to **change its UUID** to <span class="marker">AA6062F0-98CA-4211-8EC4-193EB73CEBE6</span> and update its Major/Minor ID according to its placement.

![Open Beacon Credentials]({{ site.url }}/images/post_open_beacon_credentials_rooms.svg)

Here's an example: An iBeacon placed at the fridge in your kitchen should have the Major ID 104 (Place ‣ Home ‣ Kitchen) and the Minor ID 201 (Object ‣ Appliance ‣ Fridge).

You can combine objects and rooms to your liking. You can also use your own IDs outside of the defined scope. In these cases auto-naming will fall back to more generic range based names. Just keep in mind to use the same UUID for all your iBeacons.

In general **Major IDs** are grouped by places like "Home" and "Work" broken down to rooms. **Minor IDs** are grouped by object types like "Furniture", "Appliance", "Electronics", "Wearables", etc. broken down to specific objects.

<div class="comment" style="margin-bottom:30px;">
Check out our documentation with the full set of place mappings <a href="https://github.com/AwwApps/Open-Beacon-Credentials" title="Open Beacon Credential - A shared iBeacon identifier scheme for common personal use cases">here</a>
</div>

If you need help updating your iBeacon credentials, check out our [wiki](https://github.com/AwwApps/Open-Beacon-Credentials/wiki/Configuration-Guides) with a list of configuration guides covering common vendors.

### Supporting Apps

* [Launch Here](http://launchhere.awwapps.com)
* [Travel Radar](http://travelradar.awwapps.com) (upcoming)

The upcoming updates of our apps will include full Open Beacon Credentials support. It will become our recommended way to use iBeacons with our apps. Note: We will retain support for a set of other known vendors and apply the same auto-naming rules to those. The release notes of our upcoming updates will include more details on this.

### Limitations

You should be aware that using a shared identifier implies the possibility of getting unwanted notifications caused by other people's personal iBeacons using the same credentials. We are aware of this but in fact we also see this as an opportunity to extend context-awareness to areas outside of your own beacon deployments. In the end it's all about the apps sticking to the conventions and reacting in meaningful and responsible ways.

If you have any ideas or questions (also critical ones) on this, please don’t hesitate and get in touch.

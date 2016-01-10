---
layout: "post"
title: "Clean Install Mac OS X"
date: "2016-01-10 20:50"
---

# Setup New Mac OS X Yosemite and Development Environments

## A Clean Installation of Mac OS X Yosemite

### Plan Disk Drive Partitions

Before anything get started, as SSD space is precious, we should plan how we want to allocate our disk space.

The secondary HDD can be less complex, if the primary SSD is big enough, like 256GB of space, then we can just store all musics and photos in SSD as well. But at the moment, I'll just assume we are running on a 120GB SSD.

__Primary__  
  * 120 GB **[Macintosh SSD]**
    - The primary SSD storage, where the Operating System and Apps reside.
__Secondary__  
  * 8 GB **[Installer]**
    - A partition for the installer. You can also use a USB flash drive instead.
  * 240 GB **[Time Machine]**
    - Time machine partition, double of the size of primary (OS) storage.
  * 120+ GB **[Data]**
    - Data files, store whole lot of musics, videos, photos and something like that.
  * 120 GB **[Snapshot]**
    - A bootable system snapshot (clone) for the primary (OS) storage.

While we are still running on our primary SSD, format secondary HDD into 4 partitions, adjust their size accordingly. We can do these in with `Disk Utility`.

To continue, let's make sure we already have these:
* OS X Yosemite Installer.app
* osxupdatecombo10.10.{#}.dmg
* secupd2015-{###}yosemite.dmg

Move everything (predownloaded app installers) into `/Volumes/Data`, and we are good to go.

### Create Installation Media

There is a `createinstallmedia` utility inside `OS X Yosemite.app` content folder, which can be used to create a bootable installation media.

Run the following command in `Terminal`:

```
#! /usr/bin/env bash
/Volumes/Data\ Storage/Install\ OS\ X\ Yosemite.app/contents/Resources/createinstallmedia --volume /Volumes/OS\ X\ Installer --applicationpath "/Volumes/Data Storage/Installer/Install OS X Yosemite.app"
```

### Install OS X Yosemite

1. Restart our system.
2. After the initial chime, hold down `option` key (or labeled as `alt` key), and we will see a list of bootable drives.
3. Select `Install OS X Yosemite`.
4. Select `Disk Utility`, and format our `Macintosh SSD`. Please make sure our drive partition is `GUI Partition Table`.
5. Quit `Disk Utility` and continue with the installation settings.

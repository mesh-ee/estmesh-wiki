---
title: MeshCore
description: Information about the MeshCore configurations.
published: true
date: 2026-06-01T10:18:06.156Z
tags: 
editor: markdown
dateCreated: 2026-01-21T09:32:08.576Z
---

# Companion setup

Setup is straightforward if you are using the companion app.

**Most important:** for MeshCore in Estonia, use the **EU/UK (Narrow)** preset.

That preset sets transmit power to **22 dBm**. Your device may allow higher power - check its manual.

In **Experimental Settings**, set **Default Region Scope** to `ee`. You can override this per channel and add extra scopes if needed.

> 💡 **Tip**
> MeshMapper also uses **Default Region Scope**, so all packets you send will use it. If you travel, reset it.

# Repeater and Room Server setup

These can only be configured over USB with:
* [config.meshcore.io](https://config.meshcore.io) (use **Console**)
* [meshcore-cli](https://github.com/meshcore-dev/meshcore-cli)

With slight adaptations (`name`, `lat`, `lon`, `region`), the following gives you a well-behaved node:

```
set name Endla 10A
set lat 59.429584
set lon 24.733158

set radio 869.618,62.5,8,8
set tx 22
set dutycycle 10

set path.hash.mode 1
set advert.interval 0
set flood.advert.interval 24
set loop.detect moderate
region default ee

region put harjumaa
region put tallinn
region save

clock sync
```

> 💡 **Tip**
> Do `clock sync` after each reboot to ensure proper network operation.

> 💡 **Tip**
> If your repeater is close to other repeaters (<1km), consider enabling CAD (Channel Activity Detection) with `set cad on` and increasing `txdelay` to reduce the probability of causing interference.

# Useful links

* [Tallinn K-Space Hackerspace MeshCore project documentation](https://wiki.k-space.ee/en/projects/radio/MeshCore)

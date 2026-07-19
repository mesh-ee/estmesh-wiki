---
title: Wardriving & Meshmapper
description: 
published: true
date: 2026-02-12T15:03:36.678Z
tags: 
editor: markdown
dateCreated: 2026-01-24T10:03:27.471Z
---

MeshMapper is used to map mesh coverage, repeater reach, and noise levels using wardriving data collected via MeshCore companions.  
During a wardrive, GPS-tagged messages are sent over the mesh and analyzed to determine connectivity and coverage quality.

### Useful Links

- Meshmapper Android APP: https://play.google.com/store/apps/details?id=net.meshmapper.app&pcampaignid=web_share
- Meshmapper WIKI: https://wiki.meshmapper.net/
- Wardriving Web-interface: https://wardrive.meshmapper.net/
- Estonia map view: https://tll.meshmapper.net/
- Leaderboard: https://tll.meshmapper.net/leaderboard.php

### Important Wardriving Settings

|**Setting**|**Value**|**Info**|
|---|---|---|
|External Antenna|Off (default)|Enable only if your wardriving setup uses an external antenna (e.g. vehicle-mounted antenna)|
|Ignore ID|Off (default)|Use only when a repeater is moving with you (e.g. roof-mounted car repeater) to avoid skewing coverage results|

For typical handheld or mobile companion wardriving, these settings should remain **disabled**.

---

## More Information
### Radio Power

Transmit power is **device-specific** and should be set within your hardware’s output power.

For example, some users set this to **0.3 W** to approximate devices with ~22 dBm output (such as the T3S3).  
If you are unsure, use a conservative value or refer to your device specifications.

### GPS Source

Wardriving uses the **phone’s internal GPS** for location data.

The node itself does not provide GPS coordinates for wardrive logging.  

All recorded locations are based on the mobile device running the app.


### How Wardriving Works

1. **Initiation**  
   A wardriving session is started on a mobile device and connected via Bluetooth to a MeshCore companion.  
   Sessions are authorized against known companions active within the last 60 days and are limited by available slots to reduce mesh load.

2. **The Drive**  
   The app sends timed GPS-tagged messages over the mesh.  
   These messages are received by observers and forwarded via MQTT to the MeshMapper backend.

3. **Listening**  
   The companion listens for repeaters rebroadcasting the messages and collects metadata such as location, transmit power, noise floor, repeater IDs, and raw packets.

4. **Processing & Status Classification**

   - **BIDIR** – Message received by the mesh and repeated back to the companion (two-way communication)
   - **TX** – Message received by the mesh, but no repeats heard (one-way outbound)
   - **DEAD** – Local repeat heard, but message not received by the mesh
   - **DROP** – Message not received and no repeats heard

5. **Passive RX Mapping**  
   Unrelated mesh traffic heard by the companion is also recorded, indicating inbound connectivity.

6. **Visualization**  
   Coverage data is layered on the map, with BIDIR on top and DROP on the bottom.  
   Additional layers include repeaters, terrain modes, and a noise heatmap generated from baseline noise comparisons.

This data helps monitor network health and guide infrastructure improvements.

---
title: MQTT
description: 
published: true
date: 2026-01-21T09:16:13.183Z
tags: 
editor: markdown
dateCreated: 2025-10-17T17:48:18.251Z
---

## About
Right now, the TPT node in Tallinn acts as an **MQTT bridge**.  
This means:

- All LoRa traffic that reaches TPT can be forwarded to our private MQTT broker.
- If another city, e.g., Tartu or Pärnu, sets up its own uplink/downlink node, that node becomes the other end of the bridge.
- Messages between cities always travel through **at least one bridge** (like TPT). Without a bridge, messages stay local.

![mqtt_overview.webp](/mqtt_overview.webp)

#### Why?
We believe in LoRa and want to keep its spirit alive. Not everyone needs to be on MQTT. By setting up only a few bridges, we actively encourage more nodes to be deployed across Estonia.

### How to control MQTT for your node:
- **Enable “OK to MQTT”** → Your messages can be forwarded to the broker (uplink).
- **Disable “OK to MQTT”** → Your node will never forward its packets to MQTT.
- **Disable “Ignore MQTT”** → You will receive messages that come from MQTT (downlink).
- **Enable “Ignore MQTT”** → You will not receive MQTT-delivered messages.

### In short
- **To talk with other cities:** “OK to MQTT” = **ON**, “Ignore MQTT” = **OFF**  
- **To stay purely local:** “OK to MQTT” = **OFF**

### Want to set up a bridge or just MQTT for yourself?
- If you want to set up a bridge in a city where there isn’t one yet, get in contact via **Discord**.  
- If you live far away and want some chat buddies, get in contact via **Discord** as well.

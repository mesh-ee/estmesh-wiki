---
title: Useful Info
description: 
published: true
date: 2026-03-18T11:39:42.380Z
tags: 
editor: markdown
dateCreated: 2026-01-21T10:02:10.718Z
---

# Packet Analayzer
Tallinn MeshCore has few nodes configured to forward all head packets to [analyzer.letsmesh.net](https://analyzer.letsmesh.net/packets?region=TLL) where you can view packet contents and visualize the path.

![screenshot_2026-03-18-133144_meshcore_analyzer.png](/screenshot_2026-03-18-133144_meshcore_analyzer.png)

# Bots on the Mesh

There are several bots running on the mesh that provide testing and informational functionality.  
The bot software is provided by [agessaman](https://github.com/agessaman/meshcore-bot/)

## #bot Hashtag Channel

There is a public hashtag channel called **#bot** that anyone can join.

To join:
- Go to **Add Channel**
- Select **Join a hashtag channel**
- Enter `#bot`

This channel is primarily used for interacting with these "bots" and testing bot-related features.

### Bot Comands
#### help
List of commands available
```
Bot Help: test (or t), ping, help, hello, cmd, wx, aqi, sun, moon, solar, hfcond, satpass, prefix, path, dice, roll, stats
```
#### test
```
ack @[Arti] | 73,09,3a | SNR: 2.5 dB | RSSI: -90 dBm | Round trip: 15.3km (2 segs) | 1st/last rep: 5.0km | Received at: 13:33:45
```
#### ping
```
Pong!
```

#### path
```
73: Arti Energia
81: PDVL Mustamäe Repeater
```
#### wx
Weather
```
wx Tartu,Estonia
```
```
Tartu linn, EE: Today: ☁️Overcast 5°C 75%RH 💧1°C 👁️20mi 📊1028hPa | H:6°C L:1°C | Tomorrow: 🌧️5°C/1°C 🌦️94% 3.20
```

## Automatic Map Updates

One unique feature of the bot is **automatic map updates**.

The auto map uploader has been integrated into the bot and operates as follows:
- When the bot receives an **advert** from a room or repeater, it updates the "internet map"
- Updates are rate-limited with a **cooldown of 3600 seconds (1 hour)**

This ensures the map stays up to date without causing unnecessary traffic on the mesh.

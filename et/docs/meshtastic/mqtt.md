---
title: MQTT
description: 
published: true
date: 2026-01-21T09:15:53.730Z
tags: 
editor: markdown
dateCreated: 2025-10-17T18:14:29.637Z
---

## Ülevaade
Praegu toimib TPT node Tallinnas **MQTT sillana**.  
See tähendab:

- Kõik LoRa liiklus, mis jõuab TPT-le, edastatakse meie privaatsele MQTT serverile.
- Kui teine linn, nt Tartu või Pärnu, seadistab oma MQTT silla, saab see node teiseks otsaks sillale.
- Linnadevahelised sõnumid liiguvad alati läbi **vähemalt ühe silla** (näiteks TPT). Ilma sillata jäävad sõnumid lokaalseks.

![mqtt_overview.webp](/mqtt_overview.webp)

#### Miks?
Usume LoRasse ja tahame säilitada selle hinge. Kõik nodeid ei pea olema MQTT-s. Piirates sildaded arvu julgustame, et Eestise tekkiks rohkem node.

### Kuidas MQTT-d oma sõlmes kontrollida:
- **Luba “OK to MQTT”** → Sinu sõnumeid saab edastada sillale (uplink).  
- **Keela “OK to MQTT”** → Sinu sõlme sõnumeid ei edastata MQTT-le.  
- **Keela “Ignore MQTT”** → Saad MQTT kaudu tulevaid sõnumeid (downlink).  
- **Luba “Ignore MQTT”** → Sa ei saa MQTT kaudu edastatud sõnumeid.

### Lühidalt
- **Suhtlemiseks teiste linnadega:** “OK to MQTT” = **SEES**, “Ignore MQTT” = **VÄLJAS**  
- **Ainult kohalike sõnumite jaoks:** “OK to MQTT” = **VÄLJAS**

### Tahad silda seadistada või lihtsalt MQTT-d kasutada?
- Kui soovid silda linnas, kus seda veel pole, võta ühendust **Discordis**.  
- Kui elad kaugel ja tahad mõnda jutukaaslast, võta samuti ühendust **Discordis**.

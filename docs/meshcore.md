---
title: Meshcore
description: Information about the Meshtastic configurations.
published: true
date: 2026-06-01T10:18:06.156Z
tags: 
editor: markdown
dateCreated: 2026-01-21T09:32:08.576Z
---

# Settings
## Lora

MeshCore is supported in Estonia using the EU/UK (Narrow) preset. No additional regional tuning is required beyond the settings listed below.

|**Setting**|**Value**|**Info**|
|---|---|---|
|Preset|**EU/UK (Narrow)**|Recommended preset for MeshCore operation in Estonia|
|Frequency|869.618 MHz|Within the EU SRD band|
|Bandwidth|62.5 kHz|Narrow bandwidth for improved range and reliability|
|Spreading Factor|8|Balanced range and data rate|
|Coding Rate|8|Improves robustness in noisy environments|
|Transmit Power|Device-dependent|Up to **+27 dBm (500 mW ERP)** is permitted|

## Repeater / Room server setup

Configured over USB using https://config.meshcore.io/

|**Setting**|**Value**|**Info**|
|---|---|---|
|Repeater Guest Password|*(Blank)*|Preferred for publicly accessible routers|
|Room Server Password|*(Blank)* or `hello`|Simple values recommended for ease of access|
|Location|Aproximate location|Requirement for the repeater to show up in [MeshMapper](/en/docs/meshcore/wardriving)|
|In console| `set path.hash.mode 1` | This tells the repeater to use 2byte hashes for adverts, avoiding conflicts |
|Other Settings|Default|No changes required unless you have a specific use case|

> 💡 **Tip**
> Remember to sync the repeater clock after each reboot to ensure proper network operation.

## Repeater Key Prefix Collisions

Repeater hops are identified by the **first two hexadecimal characters** of their key.  
This means there are only **255 unique combinations**, so collisions can occur in larger networks.

To reduce the chance of collisions:
- Check currently used prefixes here:  
  https://analyzer.letsmesh.net/nodes/prefix-utilization?region=TLL
- Generate a new key using:  
  https://gessaman.com/mc-keygen/

Choosing a less-used prefix helps improve routing clarity and reduces ambiguity in the mesh.


# Useful Links
* [Tallinn K-Space Hackerspace MeshCore project documentation](https://wiki.k-space.ee/en/projects/radio/MeshCore)
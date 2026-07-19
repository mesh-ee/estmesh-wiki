---
title: Meshtastic
description: Information about the Meshtastic configurations.
published: true
date: 2026-03-09T19:32:10.599Z
tags: 
editor: markdown
dateCreated: 2025-10-17T19:45:31.173Z
---

## LongFast LoRa Config
|**Setting**|**Value**|**Info**|
|---|---|---|
| Region | European Union 868MHz | 433MHz is also allowed in Estonia, though it’s not widely used yet |
|Preset|Long Range Fast|We’ve also tested using Medium Fast. You can try it as well and as long as there’s a **Medium Fast bridge** available, packets will be automatically forwarded between Medium Fast and Long Fast in the mqtt broker|
|Ignore MQTT|False|Read about this setting here [`MQTT`](/en/mqtt)|
|OK to MQTT|True|Read about this setting here [`MQTT`](/en/mqtt)|
|Number of Hops| 3-5 | You might be tempted to set the maximum number of hops (7) to get the most out of your device. However, doing so can cause instability across the entire mesh and should be avoided |

### Channel Config
We are using the default channel other than the Bot cannel. 
|**Setting**|**Value**|**Info**|
|---|---|---|
| Channel Name | LongFast | Must be exactly the same |
|LongFast| AQ==| Main chatter |
|Bot| AQ==| Testing and bot channel |

---

## EdgeFastLow LoRa Config

|**Setting**|**Value**|**Info**|
|---|---|---|
|Use preset| Disabled | There is no EFL preset in Meshtastic |
| Bandwidth | 62 kHz | |
|Spread factor| 8| |
|Coding rate| 4/8 (8) | |
|Ignore MQTT|False|Read about this setting here [`MQTT`](/en/mqtt)|
|OK to MQTT|True|Read about this setting here [`MQTT`](/en/mqtt)|
|Number of Hops| 3-5 | You might be tempted to set the maximum number of hops (7) to get the most out of your device. However, doing so can cause instability across the entire mesh and should be avoided |
|Frequency offset| 0 MHz| |
|Frequency slot| 1 | Has to be 1! |
|Frequency override| 1 | 869.4313 MHz |

### Channel config
|**Setting**|**Value**|**Info**|
|---|---|---|
| Channel Name | EdgeFastLow | Must be exactly the same! Caps sensitive |
|PSK| AQ==| |

### Screenshots for reference
![screenshot_20260216_153620_meshtastic.jpg](/screenshot_20260216_153620_meshtastic.jpg =200x)![screenshot_20260216_154247_meshtastic.jpg](/screenshot_20260216_154247_meshtastic.jpg =200x)
## Other
### Device
|**Setting**|**Value**|**Info**|
|---|---|---|
|Device Role | `CLIENT`, `CLIENT_MUTE` or `CLIENT_BASE` | You can read more about choosing the right device role [here](https://meshtastic.org/blog/choosing-the-right-device-role/). `CLIENT_BASE` nodes will always rebroadcast messages to and from your other personal nodes. Set one node to `CLIENT_BASE`. Set your other nodes (typically `CLIENT` or `CLIENT_MUTE`) as favorites on the `CLIENT_BASE` |
| Node Info Broadcast Interval | 3 h (mobile) / 12 h (static) | Recommended configuration |
|POSIX Timezone|EET-2EEST,M3.5.0/3,M.10.5.0/4 | |

### Position
For mobile nodes we suggest.
|**Setting**|**Value**|**Info**|
|---|---|---|
|Smart Position| On | Off for static nodes |
|Minimum Interval| At least 30 seconds| This is already very frequent |
| Minimum Distance | ≥ 250 m (indoor) / ≥ 150 m (outdoor) | If the minimum distance is set too low for an indoor node, it will broadcast too frequently, which can cause network congestion |

For static nodes we suggest.
|**Setting**|**Value**|**Info**|
|---|---|---|
| Fixed Position | On | To clear the location, set both latitude and longitude to 0.0 |


### Telemetry
|**Setting**|**Value**|**Info**|
|---|---|---|
| Device Metrics Update | Off / 3 h (mobile) / 12 h (static) / 1 h (solar) | Use only if LoRa battery reporting is needed. Wi-Fi/BLE companion devices already report battery % every minute |
| Environment Telemetry Enabled | User choice | Enable if a BME or similar sensor is present (typically used for monitoring temperature & humidity in outdoor nodes) |
| Environment Telemetry Interval | 6 h | Recommended interval for regular telemetry updates |
|Power Metrics Enabled| Only really applicable for solar nodes | This is for external power sensors (e.g., INA). Device metrics already contain Battery Level & Voltage |
|Power Metrics Interval| 6 h | Suggested reporting interval |
| Air Quality Enabled | User choice | If an air quality sensor or a capable one is installed (e.g., BME680) |
| Air Quality Interval | 6 h | Suggested reporting interval |


## Traceroutes
### Why am I seeing ffff or Unknown in traceroute?
Nodes with older firmware or nodes that cannot decrypt the traceroute will be displayed as **"Unknown"** or **FFFF** (ID equal to `4294967295` or `0xFFFFFFFF` in hexadecimal notation. But this doesn't seem to be always true as `4294967295` or `0xFFFFFFFF` can also mean a broadcast to `^all`.
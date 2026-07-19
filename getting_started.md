---
title: Getting Started
description: 
published: false
date: 2026-02-12T21:44:15.063Z
tags: 
editor: markdown
dateCreated: 2026-02-12T08:28:32.853Z
---



## Getting Started

Welcome! This page will help you choose the right firmware and understand the basic differences before setting up your device.

---

## Firmware Options

There are currently two primary firmware options:

|**Firmware**|**Best For**|**Summary**|
|---|---|---|
|Meshtastic|Beginner / General Use|Simple setup, active development, and reliable messaging in **small to medium-sized meshes** with minimal configuration|
|MeshCore|Tinkerer / Advanced Users|Advanced routing control, repeater behaviour customization, and detailed packet handling with less frequent firmware changes|

> There are other mesh network solutions but this will be covered in the future when they have gotten more attention.

### Meshtastic

Meshtastic is designed to be easy to use and beginner-friendly.

- Quick setup
- Minimal configuration required
- Reliable flood-based mesh routing
- Ideal for messaging and tracking
- Frequent firmware updates and active development

Meshtastic is recommended if you want to **set it up quickly and benefit from ongoing feature updates**.

Flash instructions:
- [Meshtastic Flash Guide (PC/Android)](/en/meshtastic-flash)


### MeshCore

MeshCore is designed for users who want deeper insight and control over how the mesh operates.

- Detailed routing visibility
- Advanced packet handling
- Custom repeater configuration
- Greater flexibility for experimentation
- Less frequent firmware changes

Because MeshCore updates less often, it can feel more “set and forget” once configured, requiring **less firmware maintenance**.

MeshCore is ideal if you want to **understand how packets are handled, routed, and relayed across the mesh**.

Flash instructions:
- [MeshCore Flash Guide (PC/Android)](/en/meshcore-flash)


## Meshtastic vs MeshCore

|**Feature**|**Meshtastic**|**MeshCore**|
|---|---|---|
|Ease of Setup|Very easy|Moderate|
|Advanced Configuration|Limited|Extensive|
|Routing Visibility|Basic|Detailed|
|Update Frequency|Frequent releases|Less frequent updates|
|Best For|Everyday users|Tinkerers & network testers|


## Repeaters and Network Reach

Mesh networks rely on devices relaying messages.

Your node does **not** need to reach every other node directly.  
It only needs to reach **at least one repeater** that can then forward the message further into the mesh.

If a repeater can reach the mesh, then your message can reach the mesh.

### MeshCore Note

MeshCore often works best when:

- You can reach at least one properly placed repeater
- Or you operate more than one device (for example, one fixed repeater and one mobile node)

Flood packets in MeshCore have a limited lifetime (TTL), similar to Meshtastic.

MeshCore also supports **direct messages with defined routes**, which can allow messages to travel significantly farther if a valid routing path exists.


## Which One Should You Choose?

Choose **Meshtastic** if:
- You want simplicity
- You want reliable messaging without deep configuration
- You want frequent feature updates and active development

Choose **MeshCore** if:
- You want advanced routing control
- You want insight into packet handling
- You prefer a more stable firmware that changes less frequently
- You enjoy experimenting and optimizing network behavior


## Situational Comparison: Field Use vs Fixed Infrastructure

The choice between Meshtastic and MeshCore can depend heavily on how and where the devices are used.

### Mobile / Field Use (e.g. hiking, forest, moving as a group)

If you are out and about with a small group — for example hiking in the forest — **Meshtastic forms a self-healing mesh automatically**.

- Client devices relay messages for each other
- Each node can act as a router
- The mesh dynamically adapts as people move
- No dedicated repeater is required

This makes Meshtastic especially well suited for small, mobile groups without fixed infrastructure.

In contrast, **MeshCore companion and standalone devices do not relay traffic**.  
MeshCore relies on:

- Direct device-to-device reception  
- Or properly configured repeater nodes

Without repeaters, MeshCore nodes will only communicate if they are within direct radio range of each other.


### Fixed Infrastructure (e.g. Base Camp with Elevated Repeater)

If you have a reliable repeater placed in a good elevated position — such as a base camp, tower, or hilltop — **MeshCore can operate very reliably**.

In this setup:

- End-user devices connect to the repeater
- The repeater handles forwarding and routing
- Network behavior becomes more predictable
- Advanced routing features can be utilized

In structured deployments with fixed infrastructure, MeshCore can provide stable and controlled network behaviour.


### Summary

- For **dynamic, moving groups without infrastructure** → Meshtastic is often the simpler and more resilient option.
- For **structured setups with a properly placed repeater** → MeshCore can perform very reliably and offers greater routing control.


## Next Steps

1. Choose your firmware.
2. Follow the flashing guide.
3. Configure region and channel settings.
4. Test connectivity with nearby nodes or repeaters.

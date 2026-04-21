---
date: '2026-04-11T19:43:08-04:00'
draft: true
title: '2026 Homelab Status'
slug: /2026-homelab-status
tags: ["homelab"]
---

I've been running a home lab for a few years. Like every nerd, I’ve been eyeing a few much needed upgrades. I wanted to share my current setup before I start making changes. I'll share all upgrades through my site as future posts..

## Current Equipment
The current network is a mix of old and new equipment. Last year I upgraded the network to support 10Gbps. I did this using Mikrotik switches. Choosing Mikrotik probably saved me several hundred dollars in upgrades. The firewall is a random 4 port NUC purchased off of Amazon 8+ years ago. All of the servers are reused computers. Everything sits on a utility shelf purchased from Home Depot. I do not have a rack because space is limited. I converted a small coat closet in my office into a network closet. There's power, the ISP connection, and a nice looking dual exhaust fan to help with air flow.

### Detailed Breakdown of Current Equipment
- OPNsense Firewall/router =  4x 1G ports fanless nuc
- Core Switch = Mikrotik CR309-1G-8S+ with 8x SFP+ ports, 1x 1G management port 
- Access Switch =Mikrotik CRS310-8G+2S+ with 2x SFP+ ports, 8x 2.5G ports 
- Wireless = 2x TP-Link Deco M9+ nodes
- NAS & containers = 2018 custom built desktop UnRaid Server
- Virtual Machines = Dell Optiplex 5050 small form factor Proxmox server
- Laptop = HP G9 865 (my review)
- Wireless Testing = 1x Ubiquiti AC-PRO

I also have a random assortment of laptops, monitors, and single board computers which are used as needed.

## Network Diagram 
Here’s how my network is currently laid out. It’s nothing fancy but it shows a basic data flow.
![](/img/network.png "Basic Network Diagram")

Here's the current setup in the network closet
![](/img/networkcloset.jpg "Network Closet")

## Planned Upgrades

### Wireless
This is probably at the top of my upgrades for 2026. I've been rocking the TP-Link Deco M9+ wireless mesh system for the last 5 years. It's great and has always been very reliable. As much as I enjoy the Deco M9+, it does lack a few features I would like to use. A few of those features include:
- VLANS for segmentation
- Wifi 7 for 6ghz experiments
- Enhanced logging for SIEM
- API support for MCP experiments
- Multiple wireless networks other than guest

I’m actively researching solutions to purchase. Look for a future post on my wireless upgrade project

### Firewall
As I mentioned earlier, I’m using OPNsense for firewall and routing. The current hardware running OPNsense only supports 1gb while my core switch has eight SFP+ (10gb) ports. To get around this I'm using the 1gb management port on the Mikrotik CR309-1G-8S+ as an uplink to the firewall. Upgrading the firewall hardware to support 10g would address this issue. This upgrade would also free up the management port on the core switch.


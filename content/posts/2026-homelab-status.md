---
date: '2026-04-11T19:43:08-04:00'
draft: false
title: '2026 Homelab Status'
slug: /2026-homelab-status
tags: ["homelab"]
---

I’m planning a few homelab upgrades for 2026. I wanted to document and share my current setup before I make any changes. 

## Current Equipment
My homelab is a mix of old and new equipment. Last year I upgraded the network to support 10Gbps. I did this using Mikrotik switches. Choosing Mikrotik probably saved me several hundred dollars in upgrades. I’m using OPNsense for the firewall and routing. It’s running on a random 4 port NUC I purchased off of Amazon 8+ years ago. All of the servers are reused computers. I prefer to repurpose older computers for servers in my homelab. Most of the equipment resides in my network closet. I converted a small coat closet in my office into a network closet about 2 years ago. I do not have a rack because space is limited. Instead everything sits on a utility shelf I purchased from Home Depot. The network closet has power, the ISP connection, and an AC Infinity AIRFRAME T7 cooling system. The AC Infinity is an air exhaust system installed at the top of the closet. 

### Detailed Breakdown of Current Equipment
- OPNsense =  4x 1G ports fanless nuc
- Core Switch = Mikrotik CR309-1G-8S+ (8 SFP+ ports)
- Access Switch = Mikrotik CRS310-8G+2S+
- Wireless = 2x TP-Link Deco M9+ nodes
- UnRaid = 2018 custom built desktop with SFP+ PCIe card
- Proxmox = Dell Optiplex 5050 with SFP+ PCIe card
- Laptop = HP G9 865 (my review)
- Wireless Testing = 1x Ubiquiti AC-PRO

I also have a random assortment of laptops, monitors, and single board computers which are used as needed.

## Network Diagram
Here’s how my network is currently laid out. It’s nothing fancy but it shows a basic data flow.
![](/img/network.png "Basic Network Diagram")

Here's the current setup in the network closet.
![](/img/networkcloset.jpg "Network Closet")

## Planned Upgrades

### Wireless
Upgrading the wireless is at the top of my list for 2026. I've been using the TP-Link Deco M9+ wireless mesh system for the last 5 years. It's great and has always been very reliable. As much as I enjoy the Deco M9+, it does lack a few features I would like to use at some point. Here’s a few features I would like to have.
- VLANS for segmentation
- Wifi 7 for 6ghz experiments
- Enhanced logging for SIEM
- API support for MCP experiments
- Multiple wireless networks other than guest

I’m actively researching solutions to purchase. Look for a future post on my wireless upgrade project

### Firewall
The other upgrade is the firewall hardware. As I mentioned earlier, I’m using OPNsense for firewall and routing. The current hardware running OPNsense only supports 1gb The core switch only has eight SFP+ (10gb) ports and a 1gb management port. To get around this I'm using the 1gb management port on the core switch as an uplink to the firewall. Upgrading the firewall hardware to support 10gb would address this issue. This upgrade would also free up the management port on the core switch.

## Wrapping Up
That sums up the current state of my homelab. There’s always a wishlist of upgrades or modifications for a homelab. If you’re interested in starting your own homelab check out my post on [4 Reasons to Start a HomeLab]({{< relref "4-reasons-to-start-a-homelab.md" >}}).

Look for future posts about my homelab upgrades.

Stay curious,

-Brian


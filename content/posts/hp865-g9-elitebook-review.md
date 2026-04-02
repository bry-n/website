---
date: '2024-09-06T16:31:48-05:00'
draft: false
title: 'HP865 G9 Elitebook Review'
slug: /hp865-g9-elitebook-review
tags: ["linux", "hardware"]
author: Brian
---

I’ve been using the same laptop since 2015. It’s not the only laptop I own, but it's the one I use the most. It’s the very reliable Mid-2015 15-inch MacBook Pro. Anyone familiar with the mid-2015 model knows it’s a very well-built and reliable laptop. However, I was in search of a new laptop to replace the MacBook Pro. I had a few specific requirements:

- Upgradeable RAM, storage, WiFi, etc. The more, the better.
- 15-inch display with adequate brightness and color accuracy.
- Rigid chassis as laptops with too much flex tend to break easily.

My usage requirements are pretty straightforward. I like to move around the house when working on projects and didn’t want to be confined to just my office. Hence, a 15-inch screen is a must. Linux support is also crucial, as Linux is my operating system of choice. I run Debian or Debian-based operating systems on all of my computers and servers. I'm a very casual gamer, so a dedicated Graphics Processing Unit (GPU) is not needed, which immediately ruled out all gaming laptops. Integrated AMD or Intel graphics suffice for my needs.

In the end, I purchased an HP 865 G9 Elitebook laptop. My choice was driven by two main factors. 
1. Excellant Linux hardware support.
2. Fantastic deals on HP Business Laptops.

I use an HP 865 G8 for work, which also runs a Debian-based operating system. My experience with hardware support has also been really good. Like most manufacturers, HP offers really good deals throughout the year. I purchased the laptop during HP’s Back To School Event. If you’re looking to purchase a laptop, this can be a good opportunity for some great deals.

Dell and Lenovo offer incredible Linux support as well. You can’t go wrong with any of these three manufacturers. It really comes down to personal preference. For now, my preference is HP.


> Pro Tip: Buy business-class laptops instead of consumer-class laptops. Business laptops are typically built to last longer than consumer-class laptops.


## The Laptop Hardware
The 865 G9 technical specifications are listed below:

- Ryzen 7 PRO 6850U CPU
- Radeon 680M GPU
- 32 GB DDR5 RAM, with support for up to 64 GB of RAM
- 1 TB PCIe Gen 4 NVMe SSD, with support for up to 2 TB
- Display: 400 nits brightness with 100% sRGB coverage (1920 x 1200 resolution)
- Qualcomm QCNFA765 for Wireless & Bluetooth, which is upgradeable

Here is the link to Linux Hardware profile:
https://linux-hardware.org/?probe=9620d48b2f

## The Accessories
Here are the accessories I use with the laptop:
	
- HP USB-C Dock G5 Docking Station
- LG 34in Curved Display
- Keychron K3 Pro Mechanical Keyboard
- Logitech MX Master 3 Mouse

## The Operating System
For the operating system, I picked Debian 12, which is well-known for being very stable. This has been my experience as well. The installation process was straightforward. However, you can choose whatever operating system you're most familiar with, which highlights why I prefer Linux so much. You have so many good options to choose from. Overall, I’ve been very satisfied with my decision to use Debian 12.

Hardware detection is good, with only the fingerprint reader needing extra linux packages. Everything else worked well without additional configuration. I did experience a random wireless/bluetooth issue when I first purchased the laptop. The issue was related to bad hardware (see below). It should be noted I went with the full Debian installation (Debian Live) and not the minimal installation.

Getting started with Debian: https://www.debian.org/distrib/

## Battery Life
The laptop has a 6-cell 75 Wh Lithium-Ion battery. I get approximately 6-8 hours of battery life, which is highly dependent on how I use the laptop. It charges via USB-C and does not support charging through a traditional barrel port connector.

## Display
The laptop display has brightness of 400 nits with 100% sRGB coverage and a maximum resolution of 1920 x 1200. It's bright enough for daytime use. Most of the time, I have the brightness turned down to about 50%-60%. During my constant use, not once have I wished I purchased a laptop with a better screen. Is it as good as a Retina display? No, but it doesn't disappoint either. I don't miss having a Retina display, especially since I'm not editing photos.

## Fingerprint Reader
As I mentioned earlier, the fingerprint reader is the only piece of hardware which did not work after the installation. Run the following commands to get it working.
```
sudo apt install fprintd libpam-fprintd
```
Go to Settings -> Users -> Fingerprint Login to enroll your fingerprints.

https://wiki.debian.org/SecurityManagement/fingerprint%20authentication

## Keyboard
For a laptop keyboard, it's very satisfying to type on. Business-quality laptops typically have decent keyboards. The HP EliteBook is probably one of my favorites. The keyboard backlighting is decent and helpful when I'm typing at night. All of the keyboard macros or shortcuts for sound, screen brightness, etc., work without any issue in Debian 12.

## Ports
The laptop comes with a decent amount of ports.

- 2x USB4 Type-C ports
- 2x USB 3.2 Gen 1 Type-A ports
- 1x HDMI v2.0 port
- 1x Headphone/microphone combo jack

## Speakers
The speaker cutouts are located on the bottom of the laptop, causing the sound to come out a little muffled. I think the sound would probably be better if the speaker cutouts were located on the top of the laptop, as in the previous generation (G8).

## Suspend
It works, and it works really well. I experience only a tiny amount of battery drain. I haven’t done any testing around the percentage lost over a certain amount of time. However, I will say that I was really surprised at how well it works. Linux and suspend functionality have always been hit or miss. Regardless, when I put the laptop away, I never worry about returning to a discharged battery. However, if it were left uncharged in suspend mode for several days to a week, I would expect the battery to be fully discharged.

## Web Camera/Microphone
Both the webcam and the microphone work very well. I regularly use the laptop for Zoom calls without any issues. The video quality is great, and the microphone picks up my voice very clearly

## Wireless/Bluetooth
The only issue I had with the laptop was related to the Qualcomm QCNFA765 Wireless/Bluetooth card. The wireless would randomly throttle down to ~1 MB, and Bluetooth devices refused to pair with the laptop. After some research, all signs pointed to issues with the Qualcomm QCNFA765 drivers. However, I later discovered that the issue was actually hardware-related.

As an experiment, I purchased the Intel AX210 Wireless/Bluetooth card from Amazon (link below). When it came time to swap the wireless cards, I discovered that the Qualcomm QCNFA765 was, in fact, damaged. The soldering was coming loose where antenna 2 connects to the Qualcomm card. HP support was amazing, and I received a new Qualcomm QCNFA765 within approximately 3 business days. I did run the Intel AX210 for about two weeks and did not experience the 1 MB throttling issue or Bluetooth pairing issues with the AX210 card. I eventually installed the new Qualcomm QCNFA765 wireless/Bluetooth card. The throttling issue and Bluetooth pairing issues were resolved with the new Qualcomm card.

Intel AX210 - https://a.co/d/1CtVbDj

## Final Thoughts
There's an element of fun and satisfaction when you have more control over your personal computing equipment. Overall, I'm very happy with the setup, despite the wireless card issue I encountered. I would purchase another HP EliteBook series laptop. I highly recommend the HP EliteBook line for your next Linux laptop! 

Stay curious,

-Brian

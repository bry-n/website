---
date: '2026-07-11T18:00:00-04:00'
draft: false
title: 'Arch Linux Clamshell Mode'
slug: /arch-linux-clamshell-mode
tags: ["linux"]
---

I recently found myself with a new monitor which supports power and display over USB-C. This is great because I've been working on reducing clutter on my desk.

## The Issue
I quickly discovered that putting my laptop into clamshell mode while connected over USB-C caused it to suspend. This issue could be specific to my setup or similar setups. I'm running Arch Linux with Cosmic Desktop by System76. At the time of this writing there are no clamshell settings to configure in Cosmic. 

## The Fix
The simple fix is to modify the logind.conf file. There are three lines we need to edit. The exact file path for logind.conf can be found here: `/etc/systemd/logind.conf`

### Step 1: Create a backup of logind.conf
It's highly unlikely anything bad will happen but we'll be prepared regardless.
```bash
sudo cp /etc/systemd/logind.conf /etc/systemd/logind.conf.bak
```
### Step 2: Edit logind.conf
Use whatever text editor you prefer. 
```bash
sudo nano /etc/systemd/logind.conf
```

Look for the following three lines in your logind.conf file
```conf
#HandleLidSwitch=suspend
#HandleLidSwitchExternalPower=suspend
#HandleLidSwitchDocked=ignore
```

After you find those three lines in your logind.conf file make the following changes.
```conf
HandleLidSwitch=suspend
HandleLidSwitchExternalPower=ignore
HandleLidSwitchDocked=ignore
```

To summarize the changes;
1. Uncomment or remove the `#` from all three lines
2. Change `HandleLidSwitchExternalPower` from `suspend` to `ignore`

Make sure you save your changes. Do not make any other changes unless you know what you're doing.

### Step 3: Reload logind.conf
Finally, we need to reload logind.conf. 

> __WARNING:__ Make sure you have saved all work on your Linux computer. This will kill your desktop session which can be restarted. Make sure you know how to restart your desktop or window manager.
```bash
sudo systemctl restart systemd-logind
```
## Wrapping Up
Now you should be able to put your Arch Linux laptop into clamshell mode without it going into suspend mode.

Stay curious,

-Brian
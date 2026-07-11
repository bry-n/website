---
date: '2026-07-11T18:00:00-04:00'
draft: false
title: 'Arch Linux Clamshell Mode'
slug: /arch-linux-clamshell-mode
tag: ["linux"]
---

I recently found myself with a new monitor which supports power and display over USB-C. This is great because I've been working on reducing clutter on my desk.

## The Issue
I quickly discovered putting my laptop into clamshell mode caused the laptop to go into suspend mode. This occurred when the laptop was connected over USB-C to the monitor. This issue could be specific to my setup or similar setups. I'm running Arch Linux with Cosmic Desktop by System76. At the time of this writing there are no clamshell settings to configure in Cosmic.

## The Fix
The simple fix is to modify the logind.conf file. There are three lines we need to edit. The exact file path for logind.conf can be found here: `/etc/systemd/logind.conf`

### Step 1: Create a backup of logind.conf
It's highly unlikely anything bad will happen but we'll be prepared regardless.
```
sudo cp /etc/systemd/logind.conf /etc/systemd/logind.conf.bak
```
### Step 2: Edit logind.conf
Use whatever text editor you prefer. 
```
sudo nano /etc/systemd/logind.conf
```

Look for the following three lines in your logind.conf file
```
#HandleLidSwitch=suspend
#HandleLidSwitchExternalPower=suspend
#HandleLidSwitchDocked=ignore
```

After you find those three lines in your logind.conf file make the following changes.
```
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

> __WARNING:__ Make sure you have saved all work on your Linux computer. This will kill your desktop session. In my case I'm running Cosmic DE on Arch so I just restarted Cosmic DE afterwards.
```
sudo systemctl restart systemd-logind
```
## Wrapping Up
Now you should be able to put your Arch Linux laptop into clamshell mode without it going into suspend mode.

Stay curious,

-Brian
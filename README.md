# Hackintosh for Dell Latitude 5400

---
~~**NOTE: I've got a real MacBook so this repository should not be considered up to date anymore. However, I keep my Latitude 5400 as well, with macOS installed, so if there is something really broken, let me know and I'll try my best.**~~

~~**2nd NOTE: That MacBook Pro was more unstable than my Hackintosh... But it was time to upgrade, so I got myself a Latitude 7430 (expect an EFI for this too :D). And I problably sell my 5400, so this might be the very last commit I do. Thank you all!**~~

~~**3rd NOTE: So that 7430 had Iris Xe graphics card -> No hackintoshing... But I sold it, and got a 5400 again. I am not into macOS anymore, but decided to update the repo anyhow. Enjoy!**~~

**4th NOTE: Switched to Framework, and it is again too new for hackintoshing :(**

---

*Based on OpenCore, of course.*

**WARNING: This repository now uses macOS 15 Sequoia, if you need info for Sonoma, Ventura, Montenery, or Big Sur; feel free to look at an older commit, or use tags.**

**Sequoia**: Be advised that the Intel WiFi kext was not updated to Sequoia yet. Intel cards WILL NOT work! Also, in order to upgrade to Sequoia you might have to temporarily disable the BlueToolFixup.kext in OpenCore.

![About my Mac](.img/system.png)

## Specification

| | |
|-|-|
|**CPU**|Intel i5-8265U CPU @ 1.60GHz (Whiskey Lake)|
|**RAM**|24GB DDR4 2400MHz|
|**IGPU**|Intel UHD 620|
|**SSD**|Western Digital Black NVMe 500GB|
|**ETH**|Intel I217-LM|
|**WLAN+BT**|BCM94360NG (Intel 9560NGW can also work)|
|**WWAN**|Dell DW5809e (EM7305, 4G)|
|**Audio**|Realtek ALC236|
|**Ports**|USB-C (PD+DP-AltMode), 3xUSB3.0, HDMI, microSD, Multi-Jack, DC|

## Not working

- Dedicated brightness control keys (use Fn+S/Fn+B instead)
- HDMI coldplug (hotplug is OK)
- WWAN (worked before, but looks like now it is completly deprecated in macOS)
- *Hibernation (none of Hackintoshes can do that)*

## Working

- **Everything what is not in the Not working section :D**
- Bluetooth (4.0, LE, Handoff) [out-of-the-box, no kext needed]
- WLAN [no kext needed] (recommended)
- Intel WLAN [kexts added, but not that stable]
- Ethernet
- HDMI, DisplayPort Alt Mode (all with sound, but no volume adjustment)
- USB-C (I'm using it with a docking station all the time)
- USB ports mapped, working after sleep
- TrackPad with gestures (visible as Magic Trackpad 2)
- Audio, with speaker and microphone support
- QE/CI
- Sleep
- MicroSD card reader
- TouchPad buttons
- TrackStick
- Multi-Jack (both cold- and hotplug)

## Some random text

So I made this hackintosh basically just for fun, but it seems kinda stable, so I use it as my dialy driver. I've never had crashes with it.  

Regarding the not working stuff: with some time I managed to fix almost everything, so only two things are not working, but none of them is a deal-breaker:
 - The brightness control keys are not working, eventhough I added and configured the Brightness Control kext. I kept it, as with a version upgrade they might fix it.
 - HDMI coldplug: I have no idea why is it happing... But I use a USB-C docking station, so it's not a problem at all for me. And the port itself works, just need a re-plugging, so...

I would have a sentence about Intel Wifi+BT which the 5400 contains by default: When I started this project there was no such thing as Intel Wifi support at all. During the years kexts started to appear, and now I have seen promising results. That's why I digged my stock card up, placed it back, and made my EFI compatible with it! So it will work with stock WLAN card. Eventhough I would still recommend getting a natively supported one, first because the Intel card was not so stable (usuable, but not smooth (for example slow network scanning)), secondly as they did with Ventura, Apple can rewrite the whole BT/WLAN with any upgrade. There is nothing better than natively supported hardware, even in this wild west... :)

Pull requests or suggestions are welcome! :)

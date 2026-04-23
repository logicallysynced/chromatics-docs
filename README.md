---
metaLinks:
  alternates:
    - https://app.gitbook.com/s/DpGqSy4CPpGNrMRyhQGc/
---

# Introduction

<div align="left"><img src=".gitbook/assets/chromatics_black_md.png" alt="Chromatics Logo"></div>

[![Github All Releases](https://img.shields.io/github/downloads/roxaskeyheart/Chromatics/total.svg)](https://github.com/roxaskeyheart/Chromatics/releases) [![Github Latest Releases](https://img.shields.io/github/downloads/roxaskeyheart/Chromatics/latest/total.svg)](https://github.com/roxaskeyheart/Chromatics/releases/latest) [![Latest Release](https://img.shields.io/github/release/roxaskeyheart/Chromatics.svg)](https://github.com/roxaskeyheart/Chromatics/releases/latest) [![Discord](https://img.shields.io/discord/334196655131721741.svg)](https://discord.gg/sK47yFE)

**Join our Discord:** \
[![](https://discordapp.com/api/guilds/334196655131721741/widget.png?style=banner2)](https://discord.gg/sK47yFE)



Chromatics is a third-party add-on for Final Fantasy XIV which creates lighting effects on your RGB devices. There are many different scenes and effects available including:

* HP/MP/GP/CP
* Keybinds - lights your keys depending on your mapped keybind status
* Castbar progress
* Target HP/Target Castbar progress
* Job Gauges
* Enmity Tracker
* Battle Stance
* Reactive Weather - displays static & animation weather effects
* Duty Finder Bell - flash your device when your DF pops
* Damage Flash - flash your device when you take damage
* Gold Saucer Vegas Mode
* Title screen & cutscene animations



Chromatics 3.x is built in .NET 6 and utilises the new version of Sharlayan for async FFXIV calls and RGB.NET to standardise RGB device SDK's (as opposed to manually managing them as Chromatics 2.x did)<br>

## **Important Notes**&#x20;

### _**Beta Release**_&#x20;

Chromatics 3.0 is currently in public beta, as such it is expected that there will be bugs, possibly major bugs which can cause crashes or other stability. While I've done my best to test all the features extensively for stability, every PC is different and I can't possibly account for every variation - that's why we do these Beta releases!

If you do come across issues, please let us know by posting in the [Discord](https://discord.gg/sK47yFE) channel. As Chromatics 3.x is a complete rebuild of Chromatics from the ground up and should be _considerably_ more CPU & memory efficient than 2.x. However please keep an eye on performance and report any issues you find, especially when running for a long time. <br>

### _**Device Compatibility**_&#x20;

Chromatics 2.x (and 1.x) was originally designed to work only with Razer RGB devices using a dedicated library. Over time we added vendor devices, but each of these required their own separate library to work with their vendor devices. After many years this has made the codebase very difficult to maintain and update due to managing upwards of 8 different libraries, to the point where it became impossible for me to keep them all up to date.

In Chromatics 3.x we are implementing a single library, RGB.NET that is designed to work with multiple vendors in a unified way. This will make continued development and management much easier, as well as far more memory/CPU efficient. The trade off to this is Chromatics' device compatibility will be limited to what vendors & devices RGB.NET supports.

If your device is not currently supported, please get in touch with the developers of [RGB.NET](https://github.com/DarthAffe/RGB.NET) to have it implemented.&#x20;

<mark style="color:orange;">Due to RGB.NET not supporting them, with the release of 3.0, single and multi-zone keyboards will no longer be supported.</mark>

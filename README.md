---
metaLinks:
  alternates:
    - https://app.gitbook.com/s/DpGqSy4CPpGNrMRyhQGc/
---

# Introduction

<div align="left"><img src=".gitbook/assets/chromatics_black_md.png" alt="Chromatics Logo"></div>

[![Github All Releases](https://img.shields.io/github/downloads/roxaskeyheart/Chromatics/total.svg)](https://github.com/roxaskeyheart/Chromatics/releases) [![Github Latest Releases](https://img.shields.io/github/downloads/roxaskeyheart/Chromatics/latest/total.svg)](https://github.com/roxaskeyheart/Chromatics/releases/latest) [![Latest Release](https://img.shields.io/github/release/roxaskeyheart/Chromatics.svg)](https://github.com/roxaskeyheart/Chromatics/releases/latest) [![Discord](https://img.shields.io/discord/334196655131721741.svg)](https://discord.gg/sK47yFE)

**Join our Discord:**\
[![](https://discordapp.com/api/guilds/334196655131721741/widget.png?style=banner2)](https://discord.gg/sK47yFE)

## Welcome to Chromatics 4

Chromatics is a free companion app for **Final Fantasy XIV** that turns your RGB devices into an extension of the game. Your keyboard, mouse, headset, light strips, and smart bulbs can follow what's happening on screen — reacting to your health, your job, the weather around you, and much more.

Chromatics 4 is a complete, modern rebuild of the app. It uses a new UI built on Avalonia, the latest RGB.NET release and a rebuilt backend - so it runs smoothly, looks great, and supports more hardware than ever.

## What Chromatics can do

Chromatics ships with a large library of lighting scenes and effects. A few of the highlights:

* **Player vitals** — HP, MP, GP, and CP displayed live across your keys.
* **Job Gauges** — job-specific gauges for every combat class.
* **Cast bars** — your cast and your target's cast progress.
* **Keybind lighting** — keys light up based on whether an ability is available.
* **Battle Stance** — your whole setup shifts colour the moment you enter combat.
* **Enmity Tracker** — instantly see your aggro status at a glance.
* **Reactive Weather** — zones paint themselves with static or animated weather.
* **Raid Zone Effects** — supported encounters take over your lighting with choreographed animations.
* **Audio Visualizer** — your keyboard becomes a spectrum analyser driven by the game audio.
* **Screen Capture** — ambient colours sampled from the game window spill across your devices.
* **Duty Finder Bell** — devices flash when your queue pops.
* **Damage Flash** — a sharp flash when your character takes a hit.
* **Title screen and cutscene animations** — subtle flourishes for the quieter moments.
* **Gold Saucer Vegas Mode** — because of course.

## What's new in Chromatics 4

If you're coming from Chromatics 3, the app will feel familiar but everything under the hood has been upgraded. Highlights include:

* A redesigned interface with light and dark themes.
* **First-run wizard** that walks you through picking your devices the first time you launch.
* Support for **OpenRGB** and **Philips Hue** alongside the existing vendor integrations.
* A new **Audio Visualizer** base layer.
* A new **Screen Capture** base layer.
* **Full localisation** — the app is available in English, French, German, Spanish, Japanese, Korean, and Simplified Chinese.
* **Manual import** of your Chromatics 3 layers and palette via the Import buttons on the Mappings and Palette tabs.

## Device compatibility

Chromatics uses [RGB.NET](https://github.com/DarthAffe/RGB.NET) to talk to your devices. If your device is supported by RGB.NET (or by one of the extra providers Chromatics adds), it will work with Chromatics. Supported vendors include:

* Asus
* Cooler Master
* Corsair
* Logitech
* MSI
* Novation
* Razer
* SteelSeries
* Wooting
* **OpenRGB** — any device exposed through an OpenRGB server
* **Philips Hue** — Hue bridges and compatible bulbs

{% hint style="info" %}
Single-zone and multi-zone-only keyboards only has limited support. For best compatibility, make sure your device support per-key LED illumination.
{% endhint %}

## Is Chromatics safe to use?

Yes. Chromatics reads game memory to follow what's happening in FFXIV, but it does so strictly read-only — it never writes to, modifies, or injects into the game in any way.

We still recommend not discussing third-party tools in-game, since technically any third-party interaction is discouraged by the game's terms of service. There are no reported cases of Chromatics users being warned or banned, but caution is always wise.

See the [FAQ](support/faq.md) for more detail.

## Getting started

* [Prerequisites](getting-started/prerequisites.md) — what your PC needs before installing.
* [Installation](getting-started/installation.md) — step-by-step install instructions.
* [First Launch](getting-started/first-launch.md) — what to expect the first time you open Chromatics.

If you run into trouble, the [Troubleshooting](support/troubleshooting.md) page covers the most common fixes, and our [Discord](https://discord.gg/sK47yFE) community is always happy to help.

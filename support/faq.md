---
metaLinks:
  alternates:
    - https://app.gitbook.com/s/DpGqSy4CPpGNrMRyhQGc/support/faq
---

# FAQ

Quick answers to the questions we hear most often. If you don't see yours here, try the [Troubleshooting](troubleshooting.md) page or drop by our [Discord](https://discord.gg/sK47yFE).

## General

<details>

<summary>Is Chromatics free?</summary>

Yes. Chromatics is free and open source under the [MIT License](../license.md). You can download it from the [official site](https://chromaticsffxiv.com) or from [GitHub](https://github.com/roxaskeyheart/Chromatics).

</details>

<details>

<summary>Is Chromatics safe to use with FFXIV? Could I get banned?</summary>

Chromatics reads FFXIV's memory using a library called **Sharlayan**. It is strictly **read-only** - Chromatics never writes to the game, modifies it, or injects into it in any way.

We have no reason to believe the game or Square Enix can detect Chromatics, and there are no reported cases of bans or warnings from using it. That said, FFXIV's terms of service do discourage any third-party interaction with the game client, so we recommend not discussing Chromatics (or any third-party tool) in-game.

</details>

<details>

<summary>Does Chromatics work in other games?</summary>

Chromatics is designed specifically for Final Fantasy XIV. Game-driven effects like HP, job gauges, and reactive weather won't work in other games - Chromatics wouldn't know what to react to.

</details>

<details>

<summary>Is Chromatics affiliated with Square Enix?</summary>

No. Chromatics is an independent, community-made project. It is not affiliated with, endorsed by, or sponsored by SQUARE ENIX CO., LTD. in any way.

</details>

## Devices

<details>

<summary>Is my device compatible with Chromatics?</summary>

Chromatics uses [RGB.NET](https://github.com/DarthAffe/RGB.NET) to talk to RGB hardware, plus direct integrations for OpenRGB and Philips Hue. Any device supported by RGB.NET (or by one of those extra providers) should work.

Supported vendors:

* Asus
* Cooler Master
* Corsair
* Logitech
* MSI
* Novation
* Razer
* SteelSeries
* Wooting
* OpenRGB - any device exposed through an OpenRGB server
* Philips Hue - bridges and compatible bulbs
* PlayStation - DualShock 4 and DualSense controllers
* LIFX - bulbs, multi-zone strips, and matrix devices
* QMK Keyboards (Beta) - custom keyboards running QMK firmware with Raw HID enabled
* Yeelight (Beta) - bulbs, light strips, and lamps over the local LAN
* Alienware (Beta) - AlienFX hardware on Alienware and Dell G-series machines
* Dynamic Lighting (Beta) - any device Windows exposes via the Dynamic Lighting standard (Razer, Logitech G LIGHTSYNC, ASUS ROG, HyperX, MSI, SteelSeries, HP, Omen)

If you're unsure whether your specific device model is supported, see the [RGB.NET GitHub](https://github.com/DarthAffe/RGB.NET) or ask in our [Discord](https://discord.gg/sK47yFE).

</details>

<details>

<summary>Will Chromatics work with my DualShock 4 or DualSense controller?</summary>

Yes. Both are supported as part of the **PlayStation** provider. Chromatics drives the lightbar and the five player-indicator LEDs over **USB or Bluetooth**, and treats the controller as a regular device on the Mappings tab so you can assign layers to it.

Your controller's input keeps working normally in games while Chromatics is driving the lights. Chromatics only writes to the lighting, never the input pipeline.

If your controller doesn't show up, another tool (most often **Steam Input**, **DS4Windows**, or **reWASD**) is probably holding it in exclusive mode. See [Troubleshooting → My PlayStation controller isn't lighting up](troubleshooting.md#my-playstation-controller-isnt-lighting-up).

</details>

<details>

<summary>Does Chromatics need a LIFX cloud account?</summary>

No. Chromatics talks to your LIFX devices using the **Local LAN protocol** - everything happens on your local network with no internet round-trip. You don't need a LIFX cloud account, and you don't need to sign in to anything.

You do need your LIFX devices and your PC to be on the same network. If you have your bulbs on an isolated IoT VLAN, Chromatics won't be able to find them.

</details>

<details>

<summary>What happens to my LIFX bulbs when I close Chromatics?</summary>

Chromatics records the colour and on/off state of every LIFX device the moment you start controlling it. When Chromatics releases the device - you disable LIFX in Settings, or close the app - each one is restored to that earlier state.

Translation: if your bedside lamp was a warm 2700K white before Chromatics took over, it goes back to a warm 2700K white when you close the app, even if it was mid-strobe at the time.

</details>

<details>

<summary>What happens to my Hue bulbs when I close Chromatics?</summary>

The same thing as LIFX. Chromatics records each bulb's colour and on/off state the moment it starts controlling it, and restores that state when it releases the bulb. "Releasing" covers three cases: disabling Hue in **Settings → Device Providers**, disabling an individual bulb on the **Mappings** tab, or closing the app.

</details>

<details>

<summary>My device isn't supported. Can you add it?</summary>

Chromatics relies on RGB.NET to do the vendor-specific work. If your device isn't supported there, it isn't supported in Chromatics either.

The best path is to open a feature request on the [RGB.NET GitHub](https://github.com/DarthAffe/RGB.NET). Once RGB.NET adds support, it will be added in the next Chromatics release that includes that version of the library.

</details>

<details>

<summary>Why aren't my single-zone or multi-zone keyboards supported?</summary>

RGB.NET doesn't fully support single-zone or multi-zone-only keyboards. Use per-key LED devices to get the full experience of Chromatics.

</details>

<details>

<summary>My keyboard is QWERTZ / AZERTY - will Chromatics work correctly?</summary>

Yes. Open **Settings → Appearance & Language → Keyboard Layout** and choose **QWERTZ** or **AZERTY**. Chromatics remaps your existing layers for the new layout automatically - no rebuild required.

</details>

<details>

<summary>Do I still need my RGB vendor's software installed?</summary>

Yes, for most devices. Razer Synapse, Corsair iCUE, Logitech G HUB, etc. each provide the software Chromatics talks to. Keep them installed and running in the background.

</details>

## Features and usage

<details>

<summary>What's new in Chromatics 4?</summary>

The biggest changes from Chromatics 3:

* A completely rebuilt interface with light and dark themes.
* A first-run wizard to set up your devices.
* Two new base layers: **Audio Visualizer** and **Screen Capture (Beta)**.
* Support for **OpenRGB** and **Philips Hue**.
* **QWERTZ and AZERTY** keyboard layouts now fully supported.
* **Global Brightness** control.
* Full localisation in several languages.
* A privacy-respecting, opt-out crash reporter.
* Many long-standing bug fixes - including layer settings getting lost, lighting stopping after FFXIV connects, and the Enmity Tracker showing the wrong colour.

See the [Introduction](../README.md) for a full overview.

</details>

<details>

<summary>How does Chromatics interact with the game?</summary>

Chromatics uses [Sharlayan](https://github.com/FFXIVAPP/sharlayan) to read FFXIV's memory. From that it derives things like your HP, MP, job, keybinds, weather, zone, and cast progress - everything it needs to drive the layers you've set up.

Because it reads memory, Chromatics needs to run as an administrator.

</details>

<details>

<summary>Why does Chromatics need Administrator permissions?</summary>

FFXIV's process is protected in a way that non-administrator applications can't read from. Chromatics relies on that read access to know anything about the game, so it asks to be relaunched as admin if you start it without those rights.

You can tell Chromatics to handle that silently from now on via **Settings → Advanced → Always relaunch Chromatics as Administrator**.

</details>

<details>

<summary>Can I import my Chromatics 3 setup?</summary>

You can bring your layers and colour palette across manually. Chromatics 4 stores its settings in a new location, so they **don't** carry over automatically.

**To bring your layer mappings across:**

1. Find your old `layers.chromatics3` file. It will be in the folder where Chromatics 3 was installed.
2. Open Chromatics 4 and go to the **Mappings** tab.
3. Click **Import** and select your `layers.chromatics3` file.

**To bring your colour palette across:**

1. Find your old `palette.chromatics3` file. It will be in the folder where Chromatics 3 was installed.
2. Open Chromatics 4 and go to the **Palette** tab.
3. Click **Import** and select your `palette.chromatics3` file.

You'll need to set up your effects and general settings from scratch. The rebuild changed too much under the hood for everything to carry over automatically.

</details>

<details>

<summary>How do I move Chromatics to a new PC?</summary>

Copy your `%AppData%\Chromatics\` folder from the old PC to the same location on the new one, then install Chromatics 4 there. See [Installation → Moving Chromatics to another PC](../getting-started/installation.md#moving-chromatics-to-another-pc).

</details>

## Privacy

<details>

<summary>What data does Chromatics collect?</summary>

Chromatics collects **nothing** in normal use. The only time any data leaves your PC is if you have crash reporting turned on (which is the default) and Chromatics crashes. In that case, an anonymous crash report is sent to help us diagnose the issue.

You can manage this in **Settings → Advanced → Send anonymous performance and error telemetry**. Crash reporting is always available, but sending a crash report is optional and remains your choice.

</details>

<details>

<summary>How do I opt out of crash reporting?</summary>

Open **Settings → Advanced** and turn off **Send anonymous performance and error telemetry**.

</details>

## Support

<details>

<summary>I found a bug. How do I report it?</summary>

Please file it on our [GitHub issues page](https://github.com/roxaskeyheart/Chromatics/issues) or share it in our [Discord](https://discord.gg/sK47yFE). When reporting, include your Chromatics version, your devices, and a ZIP from **Settings → Advanced → Collect Logs** if you can - it makes diagnosis much faster.

</details>

<details>

<summary>Can you add this feature?</summary>

We love feature suggestions! The best places are our [GitHub](https://github.com/roxaskeyheart/Chromatics/issues) or [Discord](https://discord.gg/sK47yFE). Please search first to see if someone has already suggested it - we keep an eye on community requests.

</details>

<details>

<summary>How can I share my layouts or palettes?</summary>

Join our [community sharing Discord](https://discord.gg/A7nXaGAK7k) for layouts and palettes. Other users post setups there that you can import directly into Chromatics.

</details>

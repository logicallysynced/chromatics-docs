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

Chromatics reads FFXIV's memory using a library called **Sharlayan**. It is strictly **read-only** — Chromatics never writes to the game, modifies it, or injects into it in any way.

We have no reason to believe the game or Square Enix can detect Chromatics, and there are no reported cases of bans or warnings from using it. That said, FFXIV's terms of service do discourage any third-party interaction with the game client, so we recommend not discussing Chromatics (or any third-party tool) in-game.

</details>

<details>

<summary>Does Chromatics work in other games?</summary>

Chromatics is designed specifically for Final Fantasy XIV. Game-driven effects like HP, job gauges, and reactive weather won't work in other games — Chromatics wouldn't know what to react to.

That said, base layers like **Audio Visualizer** and **Screen Capture** will work outside FFXIV as long as the game is running in the window Chromatics is watching (for Screen Capture) or audio is coming out of your default output device (for Audio Visualizer).

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
* OpenRGB — any device exposed through an OpenRGB server
* Philips Hue (Beta)

If you're unsure whether your specific device model is supported, see the [RGB.NET GitHub](https://github.com/DarthAffe/RGB.NET) or ask in our [Discord](https://discord.gg/sK47yFE).

</details>

<details>

<summary>My device isn't supported. Can you add it?</summary>

Chromatics relies on RGB.NET to do the vendor-specific work. If your device isn't supported there, it isn't supported in Chromatics either.

The best path is to open a feature request on the [RGB.NET GitHub](https://github.com/DarthAffe/RGB.NET). Once RGB.NET adds support, it will automatically work in the next Chromatics release that bumps to that version of the library.

</details>

<details>

<summary>Why aren't my single-zone or multi-zone keyboards supported?</summary>

RGB.NET doesn't support single-zone or multi-zone-only keyboards, only per-key devices. This was a deliberate trade-off made when Chromatics switched to RGB.NET to replace the tangle of vendor-specific SDKs the older versions had to manage.

</details>

<details>

<summary>My keyboard is QWERTZ / AZERTY — will Chromatics work correctly?</summary>

Yes. Open **Settings → Appearance & Language → Keyboard Layout** and choose **QWERTZ** or **AZERTY**. Chromatics remaps your existing layers for the new layout automatically — no rebuild required.

</details>

<details>

<summary>Do I still need my RGB vendor's software installed?</summary>

In most cases yes. Razer Synapse, Corsair iCUE, Logitech G HUB, etc. each provide the SDK that Chromatics talks to. Keep them installed and running in the background.

</details>

## Features and usage

<details>

<summary>What's new in Chromatics 4?</summary>

The biggest changes from Chromatics 3:

* A rebuilt interface with light and dark themes.
* A first-run wizard to set up your devices.
* Two new base layers: **Audio Visualizer** and **Screen Capture (Beta)**.
* Support for **OpenRGB** and **Philips Hue (Beta)**.
* **Global Brightness** control.
* Automatic updates via Velopack.
* Full localisation in several languages.
* A privacy-respecting, opt-out crash reporter.

See the [Introduction](../README.md) for a full overview.

</details>

<details>

<summary>How does Chromatics interact with the game?</summary>

Chromatics uses [Sharlayan](https://github.com/FFXIVAPP/sharlayan) to read FFXIV's memory. From that it derives things like your HP, MP, job, keybinds, weather, zone, and cast progress — everything it needs to drive the layers you've set up.

Because it reads memory, Chromatics needs to run as an administrator.

</details>

<details>

<summary>Why does Chromatics need Administrator permissions?</summary>

FFXIV's process is protected in a way that non-administrator applications can't read from. Chromatics relies on that read access to know anything about the game, so it asks to be relaunched as admin if you start it without those rights.

You can tell Chromatics to handle that silently from now on via **Settings → Advanced → Always relaunch Chromatics as Administrator**.

</details>

<details>

<summary>Can I import my Chromatics 3 setup?</summary>

Yes. The first time you run Chromatics 4 it looks for your Chromatics 3 config files, imports them, and renames the originals so they are preserved. If you ever want to import an older file by hand, the **Import** buttons in the Mappings and Palette tabs accept both `.chromatics3` and `.chromatics4` files.

</details>

<details>

<summary>How do I move Chromatics to a new PC?</summary>

Copy your `%AppData%\Chromatics\` folder from the old PC to the same location on the new one, then install Chromatics 4 there. See [Installation → Moving Chromatics to another PC](../getting-started/installation.md#moving-chromatics-to-another-pc).

</details>

## Privacy

<details>

<summary>What data does Chromatics collect?</summary>

Chromatics collects **nothing** in normal use. The only time any data leaves your PC is if you have crash reporting turned on (which is the default) and Chromatics actually crashes. In that case, an anonymous crash report is sent to help us diagnose the issue.

Crash reports contain the crash stack, the app version, and basic environment information — no personally identifying information. You can turn the feature off in **Settings → Advanced → Send anonymous crash reports and performance data**.

</details>

<details>

<summary>How do I opt out of crash reporting?</summary>

Open **Settings → Advanced** and turn off **Send anonymous crash reports and performance data**.

</details>

## Support

<details>

<summary>I found a bug. How do I report it?</summary>

Please file it on our [GitHub issues page](https://github.com/roxaskeyheart/Chromatics/issues) or share it in our [Discord](https://discord.gg/sK47yFE). When reporting, include your Chromatics version, your devices, and a ZIP from **Settings → Advanced → Collect Logs** if you can — it makes diagnosis much faster.

</details>

<details>

<summary>Can you add this feature?</summary>

We love feature suggestions! The best places are our [GitHub](https://github.com/roxaskeyheart/Chromatics/issues) or [Discord](https://discord.gg/sK47yFE). Please search first to see if someone has already suggested it — we do try to keep track of community requests.

</details>

<details>

<summary>How can I share my layouts or palettes?</summary>

Join our [community sharing Discord](https://discord.gg/A7nXaGAK7k) for layouts and palettes. Other users post setups there that you can import directly into Chromatics.

</details>

---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/DpGqSy4CPpGNrMRyhQGc/getting-started/first-launch
---

# First Launch

The first time you run Chromatics 4, a short welcome wizard guides you through selecting which RGB devices to use. Here's what to expect.

## The Welcome screen

When Chromatics opens for the first time, you'll see a **Welcome to Chromatics** dialog asking you to pick your device providers.

Each tile represents a family of RGB hardware:

* Razer
* Logitech
* Corsair
* Cooler Master
* SteelSeries
* Asus
* MSI
* Wooting
* Novation
* OpenRGB

Tick every provider you actually own hardware for. You need to pick **at least one** to continue. If you're not sure, it's safe to tick all of them — Chromatics only talks to what's actually connected.

{% hint style="info" %}
**Philips Hue** is not in the Welcome wizard because it needs a one-time pairing step with your Hue bridge. You can turn it on later from **Settings → Device Providers**.
{% endhint %}

When you're happy, click **Continue**. Chromatics will save your choices and open the main window.

## Administrator permissions

Chromatics needs elevated permissions to read game memory from Final Fantasy XIV. If it's started without those permissions, you'll see a small prompt on startup asking:

> **Would you like to relaunch as Administrator?**

* **Yes** — Chromatics closes and reopens with the rights it needs.
* **No** — Chromatics keeps running, but FFXIV-driven effects (HP, job gauges, weather, etc.) won't work.

If you click Yes, a second dialog asks whether you'd like Chromatics to **always relaunch as admin** from now on. Choose Yes to skip this prompt in the future. You can toggle this behaviour any time from **Settings → Advanced → Always relaunch Chromatics as Administrator**.

{% hint style="warning" %}
The admin prompt only appears when Chromatics is actually running without admin rights. If you launched the app as administrator yourself, or the setting is already on, you won't see it.
{% endhint %}

## The main window

Once the wizard is done, you'll land on the main Chromatics interface. It's organised into a few tabs along the top:

* **Console** — status messages and the app log.
* **Mappings** — where you design what each device does.
* **Palette** — where you customise colours.
* **Effects** — quick on/off toggles for animated effects.
* **Settings** — everything else.

Chromatics loads with a sensible default layer setup, so you can plug in, start the game, and see lighting right away. From there, explore the [Using Chromatics](../using-chromatics/console.md) section to learn how to make it your own.

## What to do next

* [Run Chromatics alongside FFXIV](running-chromatics.md)
* [Design your first layer setup](../using-chromatics/mappings.md)
* [Customise your colours with palettes](../using-chromatics/palettes.md)

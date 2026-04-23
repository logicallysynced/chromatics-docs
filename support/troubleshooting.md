---
metaLinks:
  alternates:
    - https://app.gitbook.com/s/DpGqSy4CPpGNrMRyhQGc/support/troubleshooting
---

# Troubleshooting

Most Chromatics issues come down to a handful of common causes. Work through the relevant section below, and if you're still stuck, our [Discord](https://discord.gg/sK47yFE) community is always happy to help.

{% hint style="info" %}
Before anything else, make sure you're on the latest version. Open **Settings → Advanced → Check for Updates**, and install anything that's offered.
{% endhint %}

## Chromatics won't start

**Check your prerequisites.**

* Make sure the **.NET 10 Desktop Runtime (x64)** and **Visual C++ 2015–2022 Redistributable (x64)** are both installed. See [Prerequisites](../getting-started/prerequisites.md).
* If you're using the portable ZIP, right-click the downloaded file, open **Properties**, and click **Unblock** before extracting.

**Check the console.** The [Console](../using-chromatics/console.md) tab lists any startup errors first. Read them top-to-bottom — a missing runtime or misbehaving vendor SDK usually announces itself loudly.

## Chromatics starts but nothing happens in-game

**Is Chromatics running as administrator?**

Chromatics needs admin rights to read FFXIV memory. If you dismissed the relaunch prompt earlier, restart Chromatics and accept it — or turn on **Settings → Advanced → Always relaunch Chromatics as Administrator**.

**Is the game connected?**

Check the Console tab. You should see a message indicating Chromatics has connected to FFXIV. If it hasn't, try:

* Launching FFXIV first, then Chromatics.
* Running both as administrator.
* Disabling any other FFXIV overlay or memory-reading tool temporarily to rule out conflicts.

## My device isn't detected

1. **Make sure the vendor software is installed and running.** Razer Synapse, Corsair iCUE, Logitech G HUB, etc. must be active for Chromatics to connect to that vendor's SDK.
2. **Make sure the provider is enabled.** Check **Settings → Device Providers** — the tile for your vendor should be turned on.
3. **Restart Chromatics.** Device changes in the Device Providers section take effect on restart.
4. **Check the Console.** The Console will tell you whether a vendor SDK loaded successfully, and which devices were discovered.

If your device still isn't detected, confirm it's supported by checking the [RGB.NET device list](https://github.com/DarthAffe/RGB.NET).

## Effects aren't triggering

**Is the effect enabled?** Open the [Effects](../using-chromatics/effects.md) tab and check the tile for the effect you're expecting.

**Is the layer set up correctly?** On the [Mappings](../using-chromatics/mappings.md) tab, make sure:

* The layer is enabled (the toggle in column **J**).
* The layer type matches what you expect (column **I**).
* The layer has keys assigned (the layer editor, columns **O**–**R**).
* A higher-up layer isn't painting over it — toggle layers off one at a time to narrow it down.

**Restart if you changed providers.** If you enabled or disabled device providers recently, restart Chromatics for the change to take effect.

## The Audio Visualizer isn't reacting

* It listens to the **Windows default audio output device**. Make sure that's the device playing FFXIV audio.
* If you're using a voice chat app with an exclusive capture mode, switch it to a shared mode or use a different output.
* Set a base layer to **Audio Visualizer (Beta)** on the device you want to use. Don't look for it in the Effects tab — it's a base layer, not an effect.

## Screen Capture looks wrong or is black

* Screen Capture samples the FFXIV window. Make sure FFXIV is running in **borderless windowed** or **fullscreen windowed** mode, not exclusive fullscreen.
* Restart Chromatics if FFXIV was closed and reopened while Chromatics was running.

## My keyboard lights up in the wrong positions

Chromatics defaults to a QWERTY layout. If yours is different, open **Settings → Appearance & Language → Keyboard Layout** and select **QWERTZ** or **AZERTY**. Existing mappings are remapped for you automatically.

## Everything is too bright / too dim

Use the **Global Brightness** slider in **Settings → Appearance & Language** to scale every device at once from 0% to 100%.

## I changed something and now everything is broken

1. Try **Settings → Advanced → Reset Chromatics**. This clears your configuration and starts fresh — you'll go through the First Run wizard again.
2. If you exported layer or palette files earlier, you can re-import them afterwards.

{% hint style="warning" %}
Resetting deletes your current layer and palette setup. If you might want them back, export them from the Mappings and Palette tabs first.
{% endhint %}

## Collect logs before asking for help

When you report an issue, logs make everything faster.

1. **Settings → Advanced → Collect Logs** bundles the console log, your configuration files, and basic system info into a single ZIP.
2. Share the ZIP on Discord or attach it to a [GitHub issue](https://github.com/roxaskeyheart/Chromatics/issues).
3. Include a short description of what you did and what happened.

## Where to get more help

* **[Discord](https://discord.gg/sK47yFE)** — the fastest way to reach us and the community.
* **[GitHub Issues](https://github.com/roxaskeyheart/Chromatics/issues)** — for reproducible bugs and feature requests.
* **[FAQ](faq.md)** — answers to common questions.

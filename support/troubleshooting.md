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

* Make sure the **.NET 10 Desktop Runtime (x64)** and **Visual C++ 2017–2026 Redistributable (x64)** are both installed. See [Prerequisites](../getting-started/prerequisites.md).
* If you're using the portable ZIP, right-click the downloaded file, open **Properties**, and click **Unblock** before extracting.

**Check the console.** The [Console](../using-chromatics/console.md) tab lists any startup errors first. Read them top-to-bottom - a missing runtime or a misbehaving vendor app usually announces itself loudly.

## Chromatics starts but nothing happens in-game

**Is Chromatics running as administrator?**

Chromatics needs admin rights to read FFXIV memory. If you dismissed the relaunch prompt earlier, restart Chromatics and accept it - or turn on **Settings → Advanced → Always relaunch Chromatics as Administrator**.

**Is the game connected?**

Check the Console tab. You should see a message indicating Chromatics has connected to FFXIV. If it hasn't, try:

* Launching FFXIV first, then Chromatics.
* Running both as administrator.
* Disabling any other FFXIV overlay or memory-reading tool temporarily to rule out conflicts.

## My device isn't detected

1. **Make sure the vendor software is installed and running.** Razer Synapse, Corsair iCUE, Logitech G HUB, etc. need to be active for Chromatics to talk to that vendor's lighting.
2. **Make sure the provider is enabled.** Check **Settings → Device Providers** - the tile for your vendor should be turned on.
3. **Restart Chromatics.** Device changes in the Device Providers section take effect on restart.
4. **Check the Console.** The Console will tell you which providers loaded and which devices it picked up.

If your device still isn't detected, confirm it's supported by checking the [RGB.NET device list](https://github.com/DarthAffe/RGB.NET).

## My PlayStation controller isn't lighting up

1. **Is PlayStation enabled?** Check **Settings → Device Providers → PlayStation (Beta)**. If you've just enabled it, restart Chromatics.
2. **Is anything else holding the controller?** Tools like **Steam Input**, **DS4Windows**, and **reWASD** can claim the controller in **exclusive mode**. While they have the device, Chromatics can't open it. Close the other tool, or disable its exclusive mode, then restart Chromatics.
3. **Try the other connection.** USB and Bluetooth are both supported, but if one isn't being recognised, swapping to the other is a quick way to rule out a stuck connection.
4. **Check the Console.** Chromatics logs whether each controller was opened or rejected, and why.

Your controller's input keeps working in games either way - Chromatics only writes to the lighting, never the input pipeline.

## My Hue bridge isn't being detected

1. **Same network?** Auto-discovery uses Hue's discovery service to find bridges on your local network. Your PC and the bridge need to be on the same network for it to work.
2. **Type the IP in by hand.** If auto-discovery doesn't find the bridge, the dialog has a manual entry field. Find the bridge's IP in the Hue app (Settings → My Hue System → tap your bridge) or your router's device list, and paste it in.
3. **Press the button before clicking Submit.** Pairing only succeeds within about 30 seconds of pressing the button on top of the bridge. If you miss the window, click Submit again to retry.

## A Hue bulb is missing from the adoption picker

The picker lists every bulb the bridge currently exposes. If one's missing:

* Make sure it's powered on at the wall switch.
* Open the Hue app and confirm the bulb shows up there. If the bridge can't see it, Chromatics can't either.
* Re-open the picker (toggle Hue off and on in **Settings → Device Providers**) so Chromatics queries the bridge again.

## My LIFX devices aren't showing up

1. **Same network?** Chromatics talks to LIFX over the **Local LAN protocol**, so your PC and your LIFX devices need to be on the same network. A common gotcha is bulbs being on a 2.4 GHz IoT VLAN that's isolated from the main network your PC sits on.
2. **Re-run discovery.** Toggle LIFX off and on again in **Settings → Device Providers**. The picker dialog will run a fresh discovery sweep and you can hit **Search again** for another pass.
3. **Power-cycle a stubborn device.** Some bulbs only re-broadcast on the network after a power cycle.
4. **Pick at least one device.** If you save without ticking anything, Chromatics turns the LIFX toggle back off automatically - that's by design, not a bug.

If you disable LIFX in Settings or close the app, your devices return to the colour and on/off state they were in before Chromatics took over.

## My Yeelight devices aren't showing up

1. **Turn on LAN Control in the Yeelight app.** This is the most common reason Chromatics finds nothing. Open the **Yeelight** or **Mi Home** app, tap each bulb you want to control, and switch on **LAN Control** in its settings. Bulbs without LAN Control don't respond to discovery.
2. **Check the network.** Chromatics sends an SSDP discovery packet to **239.255.255.250 on UDP port 1982**. If your router puts IoT devices on a separate VLAN that blocks multicast back to your PC, Chromatics won't see anything. Either move the bulbs onto the same network as your PC or allow multicast UDP on port 1982 between the segments.
3. **Re-run discovery.** Toggle Yeelight off and on again in **Settings → Device Providers**. The picker dialog runs a fresh sweep and you can click **Search again** for another pass without leaving the dialog.
4. **Pick at least one device.** If you save without ticking anything, Chromatics turns the Yeelight toggle back off automatically. That's by design, not a bug.

If a bulb supports **Music Mode**, Chromatics enables it on the first paint frame. Music Mode opens a TCP connection from the bulb back to Chromatics so colour updates aren't capped at 60 commands per minute. If you see `Music Mode handshake failed` in the [Console](../using-chromatics/console.md), check that no firewall on your PC is blocking inbound TCP from the bulb's IP. Chromatics falls back to the slower outbound channel automatically when Music Mode can't be set up.

Light strips paint as a single colour. The Yeelight LAN protocol doesn't expose per-zone addressing on its strip products, even on hardware that physically supports it (Lightstrip Plus and similar).

## My Alienware lighting isn't responding

1. **Quit Alienware Command Center first.** AWCC holds the AlienFX HID interface exclusively. While it's running, Chromatics can't open your AlienFX hardware. Right-click the AWCC icon in the system tray and choose **Exit**, then re-enable the Alienware provider in **Settings → Device Providers**. The Console will tell you specifically when AWCC is the blocker.
2. **Check what hardware Chromatics detected.** Three flavours of AlienFX hardware are supported: zone-based chassis (Aurora R7-R14 desktops, m15 / m17 / x15 / x17 zone laptops, Dell G7/G5), per-key notebook keyboards (Area51m-R2, m15R3 onwards, m17R3), and per-key external keyboards (AW510K, AW920K, AW768, AW410K). The Console logs which dialect Chromatics picked for each device on enable.
3. **Per-key keyboards may light the wrong physical keys.** Alienware doesn't publish a per-board key-index map for AW510K / AW920K-class boards. Chromatics ships a default ANSI 104 layout that matches most matrix-scan orders, but the firmware on your specific keyboard may enumerate keys in a different order. Open the [Mappings](../using-chromatics/mappings.md) tab and drag the keys into their correct physical positions. The mapping persists across restarts.
4. **Other AlienFX tools may be holding the device.** AlienFX Tools (T-Troll), the legacy AlienFX Editor, and any third-party AlienFX scripting tools all open the same HID interface exclusively. Close any of them before enabling the Chromatics provider.

## My Logitech keyboard or mouse isn't lighting correctly through G HUB

Logitech G HUB ships with two features that quietly hijack RGB control away from third-party apps. Both need to be turned off for Chromatics to drive your devices reliably.

1. **Disable the G HUB FFXIV game integration.** G HUB ships its own FINAL FANTASY XIV profile that takes over the keyboard whenever the game is detected. Open **G HUB**, click the gear icon (top-right) → **Settings** → **Games & Applications**, find **FINAL FANTASY XIV** in the list, and either delete the integration or turn it off. While it's enabled, G HUB intermittently overrides Chromatics' colours with its own profile.
2. **Disable Lightsync Windows Settings.** G HUB applies a Windows-wide accent-colour synchronisation by default that can also fight Chromatics for control. In **G HUB → Settings → Lightsync**, turn off **Sync with Windows accent colour** (and any other Windows-driven Lightsync option) for every device.
3. **Restart G HUB and Chromatics** after either change. G HUB's lighting service caches profiles and won't release them until it's restarted.

You should leave G HUB itself running. Chromatics talks to your Logitech devices through G HUB's SDK; if G HUB isn't running, Logitech devices won't be detected at all.

## Effects aren't triggering

**Is the effect enabled?** Open the [Effects](../using-chromatics/effects.md) tab and check the tile for the effect you're expecting.

**Is the layer set up correctly?** On the [Mappings](../using-chromatics/mappings.md) tab, make sure:

* The layer is enabled (the toggle in column **J**).
* The layer type matches what you expect (column **I**).
* The layer has keys assigned (the layer editor, columns **O**–**R**).
* A higher-up layer isn't painting over it - toggle layers off one at a time to narrow it down.

**Restart if you changed providers.** If you enabled or disabled device providers recently, restart Chromatics for the change to take effect.

## The Audio Visualizer isn't reacting

* It listens to the **Windows default audio output device**. Make sure that's the device playing FFXIV audio.
* If you're using a voice chat app with an exclusive capture mode, switch it to a shared mode or use a different output.
* Set a base layer to **Audio Visualizer (Beta)** on the device you want to use. Don't look for it in the Effects tab - it's a base layer, not an effect.

## Screen Capture looks wrong or is black

* Screen Capture samples the FFXIV window. Make sure FFXIV is running in **borderless windowed** or **fullscreen windowed** mode, not exclusive fullscreen.
* Restart Chromatics if FFXIV was closed and reopened while Chromatics was running.

## My keyboard lights up in the wrong positions

Chromatics defaults to a QWERTY layout. If yours is different, open **Settings → Appearance & Language → Keyboard Layout** and select **QWERTZ** or **AZERTY**. Chromatics remaps your existing layers for you automatically.

## Everything is too bright / too dim

Use the **Global Brightness** slider in **Settings → Appearance & Language** to scale every device at once from 0% to 100%.

## I changed something and now everything is broken

1. Try **Settings → Advanced → Reset Chromatics**. This clears your configuration and starts fresh - you'll go through the First Run wizard again.
2. If you exported layer or palette files earlier, you can re-import them afterwards.

{% hint style="warning" %}
Resetting deletes your current layer and palette setup. If you'd like to keep them, export them from the Mappings and Palette tabs first.
{% endhint %}

## Collect logs before asking for help

When you report an issue, logs make everything faster.

1. **Settings → Advanced → Collect Logs** bundles the console log, your configuration files, and basic system info into a single ZIP.
2. Share the ZIP on Discord or attach it to a [GitHub issue](https://github.com/roxaskeyheart/Chromatics/issues).
3. Include a short description of what you did and what happened.

## Where to get more help

* **[Discord](https://discord.gg/sK47yFE)** - the fastest way to reach us and the community.
* **[GitHub Issues](https://github.com/roxaskeyheart/Chromatics/issues)** - for reproducible bugs and feature requests.
* **[FAQ](faq.md)** - answers to common questions.

---
metaLinks:
  alternates:
    - troubleshooting.md
---

# Troubleshooting

Most Chromatics issues come down to a handful of common causes. Pick the section that fits your problem and work through it. If you're still stuck, our [Discord](https://discord.gg/sK47yFE) community is always happy to help.

{% hint style="info" %}
Before anything else, make sure you're on the latest version. Open **Settings → Advanced → Check for Updates** and install anything that's offered.
{% endhint %}

## Startup and game connection

<details>

<summary>Chromatics won't start</summary>

**Check your prerequisites.**

* Make sure the **.NET 10 Desktop Runtime (x64)** and **Visual C++ 2017-2026 Redistributable (x64)** are both installed. See [Prerequisites](../getting-started/prerequisites.md).
* If you're using the portable ZIP, right-click the downloaded file, open **Properties**, and click **Unblock** before extracting.

**Check the console.** The [Console](../using-chromatics/console.md) tab lists any startup errors first. Read them top-to-bottom - a missing runtime or a misbehaving vendor app usually announces itself loudly.

</details>

<details>

<summary>Chromatics starts but nothing happens in-game</summary>

**Is Chromatics running as administrator?**

Chromatics needs admin rights to read FFXIV memory. If you dismissed the relaunch prompt earlier, restart Chromatics and accept it, or turn on **Settings → Advanced → Always relaunch Chromatics as Administrator**.

**Is the game connected?**

Check the Console tab. You should see a message indicating Chromatics has connected to FFXIV. If it hasn't, try:

* Launching FFXIV first, then Chromatics.
* Running both as administrator.
* Disabling any other FFXIV overlay or memory-reading tool temporarily to rule out conflicts.

</details>

## Devices

<details>

<summary>My device isn't detected</summary>

1. **Make sure the vendor software is installed and running.** Razer Synapse, Corsair iCUE, Logitech G HUB, etc. need to be active for Chromatics to talk to that vendor's lighting.
2. **Make sure the provider is enabled.** Check **Settings → Device Providers** - the tile for your vendor should be turned on.
3. **Restart Chromatics.** Device changes in the Device Providers section take effect on restart.
4. **Check the Console.** The Console will tell you which providers loaded and which devices it picked up.

If your device still isn't detected, confirm it's supported by checking the [RGB.NET device list](https://github.com/DarthAffe/RGB.NET).

</details>

<details>

<summary>My PlayStation controller isn't lighting up</summary>

1. **Is PlayStation enabled?** Check **Settings → Device Providers → PlayStation**. If you've just enabled it, restart Chromatics.
2. **Is anything else holding the controller?** Tools like **Steam Input**, **DS4Windows**, and **reWASD** can claim the controller in **exclusive mode**. While they have the device, Chromatics can't open it. Close the other tool, or disable its exclusive mode, then restart Chromatics.
3. **Try the other connection.** USB and Bluetooth are both supported. If one isn't being recognised, swap to the other to rule out a stuck connection.
4. **Check the Console.** Chromatics logs whether each controller was opened or rejected, and why.

Your controller's input keeps working in games either way. Chromatics only writes to the lighting, never the input pipeline.

</details>

<details>

<summary>My Hue bridge isn't being detected</summary>

1. **Same network?** Auto-discovery uses Hue's discovery service to find bridges on your local network. Your PC and the bridge need to be on the same network for it to work.
2. **Type the IP in by hand.** If auto-discovery doesn't find the bridge, the dialog has a manual entry field. Find the bridge's IP in the Hue app (Settings → My Hue System → tap your bridge) or your router's device list, and paste it in.
3. **Press the button before clicking Submit.** Pairing only succeeds within about 30 seconds of pressing the button on top of the bridge. If you miss the window, click Submit again to retry.

</details>

<details>

<summary>A Hue bulb is missing from the adoption picker</summary>

The picker lists every bulb the bridge currently exposes. If one's missing:

* Make sure it's powered on at the wall switch.
* Open the Hue app and confirm the bulb shows up there. If the bridge can't see it, Chromatics can't either.
* Re-open the picker (toggle Hue off and on in **Settings → Device Providers**) so Chromatics queries the bridge again.

</details>

<details>

<summary>My LIFX devices aren't showing up</summary>

1. **Same network?** Chromatics talks to LIFX over the **Local LAN protocol**, so your PC and your LIFX devices need to be on the same network. A common gotcha is bulbs sitting on a 2.4 GHz IoT VLAN that's isolated from the main network your PC's on.
2. **Re-run discovery.** Toggle LIFX off and on again in **Settings → Device Providers**. The picker dialog will run a fresh discovery sweep and you can hit **Search again** for another pass.
3. **Power-cycle a stubborn device.** Some bulbs only re-broadcast on the network after a power cycle.
4. **Pick at least one device.** If you save without ticking anything, Chromatics turns the LIFX toggle back off automatically. That's by design, not a bug.

If you disable LIFX in Settings or close the app, your devices return to the colour and on/off state they were in before Chromatics took over.

</details>

<details>

<summary>My Yeelight devices aren't showing up</summary>

1. **Turn on LAN Control in the Yeelight app.** This is the most common reason Chromatics finds nothing. Open the **Yeelight** or **Mi Home** app, tap each bulb you want to control, and switch on **LAN Control** in its settings. Bulbs without LAN Control don't respond to discovery.
2. **Check the network.** Chromatics sends an SSDP discovery packet to **239.255.255.250 on UDP port 1982**. If your router puts IoT devices on a separate VLAN that blocks multicast back to your PC, Chromatics won't see anything. Either move the bulbs onto the same network as your PC or allow multicast UDP on port 1982 between the segments.
3. **Re-run discovery.** Toggle Yeelight off and on again in **Settings → Device Providers**. The picker dialog runs a fresh sweep and you can click **Search again** for another pass without leaving the dialog.
4. **Pick at least one device.** If you save without ticking anything, Chromatics turns the Yeelight toggle back off automatically. That's by design, not a bug.

If a bulb supports **Music Mode**, Chromatics enables it on the first paint frame. Music Mode opens a TCP connection from the bulb back to Chromatics so colour updates aren't capped at 60 commands per minute. If you see `Music Mode handshake failed` in the [Console](../using-chromatics/console.md), check that no firewall on your PC is blocking inbound TCP from the bulb's IP. Chromatics falls back to the slower outbound channel automatically when Music Mode can't be set up.

Light strips paint as a single colour. The Yeelight LAN protocol doesn't expose per-zone addressing on its strip products, even on hardware that physically supports it (Lightstrip Plus and similar).

</details>

<details>

<summary>My Nanoleaf controller won't pair or isn't found</summary>

1. **Discovery is filtered.** Chromatics finds controllers over mDNS. If your router blocks multicast between segments (common when IoT devices sit on a separate VLAN), the sweep comes up empty. Type the controller's IP in the field at the bottom of the pairing dialog and click **Add by IP** instead - the controller's IP is in the Nanoleaf app under the device settings, or in your router's client list.
2. **Hold the button long enough.** Pairing only works while the controller is in pairing mode. Hold the power button on the controller until the lights start flashing, then release. Chromatics polls for about 30 seconds; if it times out, click **Pair** again and re-trigger the flash.
3. **The controller was reset.** If a previously-paired controller stops working, its token was invalidated (a factory reset or removal from the Nanoleaf app does this). Remove it in the pairing dialog and pair again.
4. **Essentials aren't supported.** Nanoleaf bulbs and lightstrips (the Essentials line) use Matter/Thread, not the OpenAPI, so Chromatics can't control them.

</details>

<details>

<summary>My Nanoleaf came back to the wrong scene after closing Chromatics</summary>

Chromatics captures the scene the controller was showing when it took over and re-selects it by name on close. Two cases restore something else:

1. **A different app owned the lights.** If another program was streaming to the controller (its own external-control session) when Chromatics started, that live state can't be recovered - Chromatics restores the last scene the controller itself was showing.
2. **The close was cut short.** Restore runs during shutdown with a few-seconds budget per controller. If the controller was briefly unreachable at that moment, the restore is skipped. Re-selecting the scene in the Nanoleaf app fixes it, and the next normal close restores correctly.

</details>

<details>

<summary>My Alienware lighting isn't responding</summary>

1. **Quit Alienware Command Center first.** AWCC holds the AlienFX HID interface exclusively. While it's running, Chromatics can't open your AlienFX hardware. Right-click the AWCC icon in the system tray, choose **Exit**, then re-enable the Alienware provider in **Settings → Device Providers**. The Console will tell you specifically when AWCC is the blocker.
2. **Check what hardware Chromatics detected.** Chromatics supports three flavours of AlienFX hardware: zone-based chassis (Aurora R7-R14 desktops, m15 / m17 / x15 / x17 zone laptops, Dell G7/G5), per-key notebook keyboards (Area51m-R2, m15R3 onwards, m17R3), and per-key external keyboards (AW510K, AW920K, AW768, AW410K). The Console logs which dialect Chromatics picked for each device on enable.
3. **Per-key keyboards can light the wrong physical keys.** Alienware doesn't publish a per-board key-index map for AW510K / AW920K-class boards. Chromatics ships a default ANSI 104 layout that matches most matrix-scan orders, but the firmware on your specific keyboard can enumerate keys in a different order. Open the [Mappings](../using-chromatics/mappings.md) tab and drag the keys into their correct physical positions. The mapping persists across restarts.
4. **Other AlienFX tools can hold the device too.** AlienFX Tools (T-Troll), the legacy AlienFX Editor, and any third-party AlienFX scripting tools all open the same HID interface exclusively. Close any of them before enabling the Chromatics provider.

</details>

<details>

<summary>My Windows Dynamic Lighting devices aren't showing up</summary>

1. **Turn Dynamic Lighting on in Windows Settings.** Open **Settings → Personalization → Dynamic Lighting** and confirm the master toggle is on. Compatible devices appear in the device list on that page. If a device isn't listed there, Windows doesn't see it as Dynamic-Lighting-capable and Chromatics can't pick it up either.
2. **Update Windows.** Windows Dynamic Lighting needs Windows 11 23H2 or later. Earlier builds either don't expose the LampArray API at all or expose a stub that returns no devices.
3. **Update device firmware.** Some OEMs shipped Dynamic Lighting support via firmware updates rather than out-of-the-box. If your Razer / Logitech / ASUS / etc. device works in its vendor app but isn't listed in Windows' Dynamic Lighting page, check the vendor's site for a firmware update.
4. **Check the Chromatics Console.** When the Dynamic Lighting provider enumerates devices, it logs each adopted device by name. It also logs every device it skipped, and why - usually because the conservative conflict-handling option in **Settings → Advanced** is on and a vendor provider already owns that device.

</details>

<details>

<summary>My Razer / Logitech device shows under Dynamic Lighting in Windows but not in Chromatics</summary>

Open **Settings → Advanced** and check the **Allow Dynamic Lighting to control devices already covered by another Chromatics provider** toggle. When it's off (the conservative mode), Chromatics deliberately hides Dynamic Lighting entries for any device whose vendor provider (Razer, Logitech, ASUS, MSI, SteelSeries) is enabled, so the two providers don't fight for the same hardware. Turn the toggle back on if you want Dynamic Lighting to also adopt those devices.

If you'd rather Dynamic Lighting take exclusive control of a specific device, disable that device's vendor provider in **Settings → Device Providers** instead.

</details>

<details>

<summary>Dynamic Lighting devices flicker when both the vendor provider and Dynamic Lighting are enabled</summary>

Both providers are writing to the same physical device every frame. Open **Settings → Advanced**, turn off **Allow Dynamic Lighting to control devices already covered by another Chromatics provider**, then restart Chromatics. Dynamic Lighting will silently skip overlapping devices and the vendor SDK keeps exclusive control of them.

</details>

<details>

<summary>My Logitech keyboard or mouse isn't lighting correctly through G HUB</summary>

Logitech G HUB ships with two features that quietly hijack RGB control away from third-party apps. Turn both off for Chromatics to drive your devices reliably.

1. **Disable the G HUB FFXIV game integration.** G HUB ships its own FINAL FANTASY XIV profile that takes over the keyboard whenever the game is detected. Open **G HUB**, click the gear icon (top-right) → **Settings** → **Games & Applications**, find **FINAL FANTASY XIV** in the list, and either delete the integration or turn it off. While it's enabled, G HUB intermittently overrides Chromatics' colours with its own profile.
2. **Disable Lightsync Windows Settings.** G HUB applies a Windows-wide accent-colour synchronisation by default that can fight Chromatics for control. In **G HUB → Settings → Lightsync**, turn off **Sync with Windows accent colour** (and any other Windows-driven Lightsync option) for every device.
3. **Restart G HUB and Chromatics** after either change. G HUB's lighting service caches profiles and won't release them until it's restarted.

Leave G HUB itself running. Chromatics talks to your Logitech devices through G HUB's SDK; if G HUB isn't running, Logitech devices won't be detected at all.

</details>

<details>

<summary>My QMK keyboard isn't detected</summary>

1. **Is QMK enabled?** Check **Settings → Device Providers → QMK (Beta)**. If you've just enabled it, restart Chromatics so the device scan re-runs.
2. **Close VIA, Vial, and OpenRGB before enabling.** All three open the Raw HID interface in exclusive mode while they're running. Chromatics can't share the interface with them. Exit those apps from their tray icons, then re-toggle the QMK provider.
3. **Confirm the firmware exposes Raw HID.** VIA-compatible QMK builds ship with Raw HID on by default. Firmware compiled without `RAW_ENABLE = yes` in `rules.mk` won't expose the interface and Chromatics can't talk to it.
4. **Check the Console.** Chromatics logs every HID device on the USB bus, which ones expose the Raw HID interface, and which responded to the handshake. The `[QMK] Discovery done:` line at the end of the scan summarises the breakdown by count.

</details>

<details>

<summary>My QMK keyboard shows one colour at a time instead of per-key</summary>

Stock QMK firmware works this way. The VIA protocol that ships with VIA-compatible QMK builds only exposes one RGB matrix base colour for the whole device, so the keyboard acts as a single zone. Chromatics's keyboard layers still paint normally - the device renders them as one colour.

Per-LED control needs the **OpenRGB-QMK firmware module** compiled into your QMK build. It's a third-party add-on, not part of stock QMK; you compile it into a custom QMK firmware image and flash that onto your device yourself. Once flashed, Chromatics's handshake detects the module on the next launch and switches the device to per-LED direct mode.

Chromatics does not provide instructions, support, or pre-built firmware images for the OpenRGB-QMK firmware module. Building and flashing custom firmware is between you, your device's QMK keymap, and the OpenRGB-QMK project. A bad flash can brick a device - only attempt this if you can recover from one.

**What goes into a build that Chromatics will detect**

The OpenRGB-QMK firmware module is three source files plus build wiring. The canonical source is the [Kasper24/QMK-OpenRGB](https://github.com/Kasper24/QMK-OpenRGB) fork on the `openrgb` branch. The protocol Chromatics speaks at handshake is `OPENRGB_PROTOCOL_VERSION 0xC`; firmware modules at that protocol version are detected automatically.

Source files (copy across into your QMK tree):

* `quantum/openrgb.c` - the Raw HID command handler.
* `quantum/openrgb.h` - protocol header.
* `quantum/rgb_matrix/animations/openrgb_direct_anim.h` - the `OPENRGB_DIRECT` rgb_matrix effect Chromatics drives in per-LED mode.

Build-system edits:

* `builddefs/common_features.mk` - add the `OPENRGB_ENABLE` block (force-enables `RAW_ENABLE`, adds `openrgb.c` to `SRC`, defines `-DOPENRGB_ENABLE`).
* `builddefs/show_options.mk` - list `OPENRGB_ENABLE` so it shows in the build banner.
* `quantum/rgb_matrix/animations/rgb_matrix_effects.inc` - include `openrgb_direct_anim.h` so the `OPENRGB_DIRECT` effect registers.

In your keymap's `rules.mk`:

```
OPENRGB_ENABLE = yes
VIA_ENABLE = no
OPT_DEFS += -DRAW_EPSIZE=64
```

`OPENRGB_ENABLE` and `VIA_ENABLE` cannot coexist - both want exclusive ownership of the Raw HID receive endpoint. Chromatics is fine without VIA on the device; the OpenRGB-QMK protocol covers everything Chromatics needs.

The `RAW_EPSIZE=64` line is the easy one to miss and the hardest to debug if missed. `quantum/openrgb.h` defines `RAW_EPSIZE 64` locally, but that only covers `openrgb.c`'s translation unit. The USB descriptor and `usb_main.c::send_raw_hid` read their `RAW_EPSIZE` from `tmk_core/protocol/usb_descriptor.h`, which defaults to `32`. The build looks clean and the keyboard enumerates fine, but `send_raw_hid` then drops every OpenRGB reply at its `if (length != RAW_EPSIZE) return;` check (32 in that file, 64 in openrgb.c's send buffer). Chromatics's QMK provider logs the handshake timeout and includes the same fix in its error message; the docs-side fix is to put the `OPT_DEFS` line in your keymap rules.mk so the 64 propagates to every translation unit.

`tmk_core/protocol/usb_descriptor.h:315` ships unguarded:

```c
#define RAW_EPSIZE 32
```

QMK builds with `-Werror`, so adding `-DRAW_EPSIZE=64` to OPT\_DEFS will collide and fail with `"RAW_EPSIZE" redefined`. Wrap the existing define in an `#ifndef` guard so OPT\_DEFS wins:

```c
#ifndef RAW_EPSIZE
#    define RAW_EPSIZE 32
#endif
```

This is a one-line change against a TMK protocol header that's shared with mainline QMK. Anyone porting OpenRGB-QMK to modern Keychron-fork (or mainline) QMK needs it; the upstream guard fix has not been merged.

**Forward-port gotchas if you're starting from the 2022-era Kasper24 fork**

The original OpenRGB-QMK fork targets a 2022 snapshot of QMK. To compile against current QMK (2024 onwards), three small renames are needed in the copied source:

* `DRIVER_LED_TOTAL` → `RGB_MATRIX_LED_COUNT` (renamed in upstream QMK; the old name was removed).
* `raw_hid_receive(uint8_t *data, uint8_t length)` → `raw_hid_receive(uint8_t src, uint8_t *data, uint8_t length)` (a `src` argument was added to disambiguate USB vs wireless transports).
* `keymaps[0][row][col]` → `keymap_key_to_keycode(0, (keypos_t){.row = row, .col = col})` (direct keymap-array access was replaced with an accessor function).

**Vendor-specific Raw HID conflicts**

Keychron's QMK fork at `keyboards/keychron/common/keychron_raw_hid.c` ships its own `raw_hid_receive` implementation for the Keychron Launcher web app. Adding the OpenRGB-QMK module to a Keychron-fork build produces a multiple-definition link error. Gate Keychron's implementation behind `#if !defined(OPENRGB_ENABLE)` so the OpenRGB handler wins when the flag is set. Other vendor forks may have similar conflicts - any `raw_hid_receive` definition outside `quantum/` needs gating.

**Tradeoff to know about.** OpenRGB-QMK takes over the Raw HID endpoint, which disables vendor companion apps that use the same endpoint (Keychron Launcher, VIA itself, etc.) on the same firmware. To switch back, flash a stock firmware image.

</details>

<details>

<summary>My QMK macropad or knob board only shows one LED in Mappings</summary>

QMK macropads, knob boards, and similar non-keyboard devices running stock QMK firmware act as a single-zone device through VIA. Chromatics exposes them as a single Custom1 LED so you can drive their lighting from the Mappings tab without phantom keyboard keys cluttering the view.

If your device has more than one physical LED and you want individual control over each, you need the OpenRGB-QMK firmware module compiled into the firmware. See _My QMK keyboard shows one colour at a time instead of per-key_ above for context and disclaimers.

</details>

<details>

<summary>My QMK keyboard's keys light the wrong physical positions</summary>

VIA-only QMK keyboards use a synthetic ANSI 104 key layout because VIA doesn't expose per-LED addressing - all keys map to the firmware's single matrix colour anyway, so the layout exists only so Chromatics's keyboard effects have something to paint against. The wrong-physical-key complaint only applies to firmware with the OpenRGB-QMK module flashed, where Chromatics drives each LED individually.

If you've flashed OpenRGB-QMK and the wrong physical keys light up, Chromatics ships a pre-built key layout database covering 2650 QMK boards (sourced from www.caniusevia.com keymaps). For boards outside that database, open the [Mappings](../using-chromatics/mappings.md) tab and drag each key into its correct physical position. The mapping persists across restarts.&#x20;

</details>

## Redragon mice (Beta)

<details>

<summary>My Redragon mouse isn't detected</summary>

1. **Is Redragon enabled?** Check **Settings → Device Providers → Redragon (Beta)**. If you've just enabled it, restart Chromatics so the device scan re-runs.
2. **Close OpenRGB, Razer Synapse, or the Redragon utility before enabling.** All three open the HID interface in exclusive mode while running. Chromatics can't share the interface with them.
3. **Plug the mouse in directly.** Some USB hubs strip the vendor-defined HID interfaces Chromatics needs. Try a direct port on your PC.
4. **Check the model is supported.** Chromatics covers the 13 mice listed in the [Settings page](../using-chromatics/settings.md#redragon-beta). Other Redragon mice use different protocols and are not handled by this provider.

</details>

<details>

<summary>My Redragon mouse flickers under fast colour changes</summary>

Each frame Chromatics sends two HID feature reports - a colour write to register `0x0449` and an apply commit (`0xF1`). The firmware briefly dips PWM output on every commit while it re-reads the colour register. At 30 frames per second those dips read as continuous flicker on most hardware. The M908 Impact shows it most clearly.

The v4.2.64 default cuts the per-frame cadence to 15 frames per second so the dips fall below perception while cycling effects stay smooth. If you still see flicker on v4.2.64 or later, edit `redragonUpdateRateHz` in `settings.chromatics4` (see the hidden settings table in [Settings → Where are the old "Advanced Settings"?](../using-chromatics/settings.md#where-are-the-old-advanced-settings)) and drop the value further. `5` or `10` are good next steps; the setting is clamped to `1`-`30`.

{% hint style="info" %}
If you saw this on v4.2.62 or v4.2.63, those builds shipped an earlier (incomplete) fix that aimed at duplicate HID handles. The actual cause is the per-frame commit cadence, addressed in v4.2.64.
{% endhint %}

</details>

<details>

<summary>My Redragon mouse only shows one LED in Mappings</summary>

Every Redragon mouse on this protocol exposes one addressable colour zone. The logo and DPI underglow share the same firmware register, so Chromatics models them as a single LED. There is no per-LED control on this hardware. Map the single LED to whichever layer you want via the Mappings tab.

</details>

## EVision keyboards (Beta)

<details>

<summary>My EVision-family keyboard isn't detected</summary>

1. **Is EVision enabled?** Check **Settings → Device Providers → EVision (Beta)**. If you've just enabled it, restart Chromatics so the device scan re-runs.
2. **Close OpenRGB and the vendor utility before enabling.** Glorious Core, the Redragon utility, and any other lighting software hold the HID interface exclusively while running. Chromatics can't share the interface with them.
3. **Check the model is supported.** Chromatics covers the 13 keyboards listed in the [Settings page](../using-chromatics/settings.md#evision-beta). The Redragon K530 Draconic Pro and K568 Dark Avenger are NOT in the list - their PIDs are not in OpenRGB's detection table and we cannot add them safely without confirmed hardware.
4. **Check the Console.** The `[EVision] Discovery resolved N candidate(s):` line at the end of the scan lists every detected keyboard with its USB device path. If your keyboard's VID is `0x0C45` or `0x320F` but it isn't on that list, the PID does not match any entry in the supported table.

</details>

<details>

<summary>Will running dynamic effects damage my EVision keyboard?</summary>

The V1 protocol the EVision provider speaks writes to the keyboard's storage chip on every colour change. Static colours and slow effects cost nothing. Continuous fast-changing effects (spectrum cycle, audio visualizer, raid animations) write the chip hundreds of times per minute. Over years of continuous use, that wear could shorten the chip lifespan.

The community has driven these keyboards through the same protocol via OpenRGB for years and has not reported widespread storage-chip failures. The trade-off is real but the practical risk is small for typical use.

If you mostly run static colours or slow effects, you have nothing to worry about. If you plan to run fast-changing effects continuously for hours every day, you have two options:

* **Switch the keyboard off on the Mappings tab when you do not need it.** The toggle stops the writes immediately.
* **Lower the update rate.** Edit `eVisionUpdateRateHz` in `settings.chromatics4` (see the hidden settings table in [Settings → Where are the old "Advanced Settings"?](../using-chromatics/settings.md#where-are-the-old-advanced-settings)). The default is 10. Drop to 5 or lower if you want minimum wear.

</details>

<details>

<summary>My EVision keyboard's keys light the wrong physical positions</summary>

The firmware exposes 126 LED slots in a fixed wire order that does not match any specific keyboard's physical scan order. Chromatics names each slot as a Custom LedId because the OEM rebrands ship the same firmware on physically different keyboards. There is no per-board key-name table.

Open the [Mappings](../using-chromatics/mappings.md) tab and drag each LED into its correct physical position on your keyboard. The mapping persists across restarts.

</details>

## Effects and lighting

<details>

<summary>Effects aren't triggering</summary>

**Is the effect enabled?** Open the [Effects](../using-chromatics/effects.md) tab and check the tile for the effect you're expecting.

**Is the layer set up correctly?** On the [Mappings](../using-chromatics/mappings.md) tab, make sure:

* The layer is enabled (the toggle in column **J**).
* The layer type matches what you expect (column **I**).
* The layer has keys assigned (the layer editor, columns **O**-**R**).
* A higher-up layer isn't painting over it - toggle layers off one at a time to narrow it down.

**Restart if you changed providers.** If you enabled or disabled device providers recently, restart Chromatics for the change to take effect.

</details>

<details>

<summary>The Audio Visualizer isn't reacting</summary>

* It listens to the **Windows default audio output device**. Make sure that's the device playing FFXIV audio.
* If you're using a voice chat app with an exclusive capture mode, switch it to a shared mode or use a different output.
* Set a base layer to **Audio Visualizer (Beta)** on the device you want to use. Don't look for it in the Effects tab - it's a base layer, not an effect.

</details>

<details>

<summary>Screen Capture looks wrong or is black</summary>

* Screen Capture samples the FFXIV window. Make sure FFXIV is running in **borderless windowed** or **fullscreen windowed** mode, not exclusive fullscreen.
* Restart Chromatics if FFXIV was closed and reopened while Chromatics was running.

</details>

<details>

<summary>My keyboard lights up in the wrong positions</summary>

Chromatics defaults to a QWERTY layout. If yours is different, open **Settings → Appearance & Language → Keyboard Layout** and select **QWERTZ** or **AZERTY**. Chromatics remaps your existing layers for you automatically.

</details>

<details>

<summary>Everything is too bright / too dim</summary>

Use the **Global Brightness** slider in **Settings → Appearance & Language** to scale every device at once from 0% to 100%.

</details>

## Reset and recovery

<details>

<summary>I changed something and now everything is broken</summary>

1. Try **Settings → Advanced → Reset Chromatics**. This clears your configuration and starts fresh - you'll go through the First Run wizard again.
2. If you exported layer or palette files earlier, you can re-import them afterwards.

{% hint style="warning" %}
Resetting deletes your current layer and palette setup. If you'd like to keep them, export them from the Mappings and Palette tabs first.
{% endhint %}

</details>

## Get help

<details>

<summary>Collect logs before asking for help</summary>

When you report an issue, logs make everything faster.

1. **Settings → Advanced → Collect Logs** bundles your diagnostic data into a single ZIP at a location you pick. The bundle includes the Console output, your config files, and a short system-info text file. See [Privacy Policy → Diagnostic log bundles](../privacy.md#diagnostic-log-bundles-you-choose-to-share) for the full list and a note on what's worth reviewing before you share.
2. Share the ZIP on Discord or attach it to a [GitHub issue](https://github.com/logicallysynced/Chromatics/issues).
3. Include a short description of what you did and what happened.

</details>

<details>

<summary>Where to get more help</summary>

* [**Discord**](https://discord.gg/sK47yFE) - the fastest way to reach us and the community.
* [**GitHub Issues**](https://github.com/logicallysynced/Chromatics/issues) - for reproducible bugs and feature requests.
* [**FAQ**](faq.md) - answers to common questions.

</details>

---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/DpGqSy4CPpGNrMRyhQGc/getting-started/installation
---

# Installation

Chromatics 4 is available in two flavours. Both download from the same place — pick whichever suits you.

* **Installer** — the recommended option for most people. Sets everything up automatically and handles updates in the background.
* **Portable (ZIP)** — a self-contained copy you can run from any folder. Useful if you want to keep Chromatics on a USB drive or don't want anything installed to Program Files.

You can download the latest version from [GitHub](https://github.com/roxaskeyheart/Chromatics/releases/latest).

## Installer version

1. Download the latest **Chromatics Setup.exe** from the download page.
2. Run the installer and follow the on-screen prompts.
3. When the installer finishes, Chromatics is ready to launch from your Start Menu or desktop shortcut.

The installer will also register Chromatics so it can update itself automatically in the future.

{% hint style="info" %}
The installer places Chromatics in a user-writable folder so updates can be applied without needing administrator rights. Your settings live in a separate location (see [Where your settings are stored](#where-your-settings-are-stored) below), so they survive updates and reinstalls.
{% endhint %}

## Portable version

1. Download the **Chromatics Portable.zip** from the download page.
2. **Right-click the ZIP file, choose Properties, and tick "Unblock"** if you see that option. This is a Windows security quirk — skipping it will sometimes cause parts of Chromatics to misbehave.
3. Extract the ZIP to a folder of your choice.
4. Double-click **Chromatics.exe** to start the app.

{% hint style="warning" %}
The portable version still reads and writes your settings to your Windows user profile (see below), not the folder it lives in. This means your settings **persist** even if you move the portable folder or replace it with a newer version.
{% endhint %}

## Where your settings are stored

Chromatics stores all of its configuration in your Windows user profile, not next to the application. You can find it here:

```
%AppData%\Chromatics\
```

You can paste that path into the Windows Explorer address bar to jump straight there. Inside you will find four files:

| File | What it stores |
| --- | --- |
| `layers.chromatics4` | Your mapped layers for each device. |
| `palette.chromatics4` | Your custom colour palettes. |
| `effects.chromatics4` | Your Effects tab toggles. |
| `settings.chromatics4` | General and advanced app settings. |

This folder is the right one to back up if you want to move Chromatics to another PC.

## Upgrading from Chromatics 3

Chromatics 4 stores your settings in a new location on your computer, and **your previous settings will not be carried across automatically**. You can bring your layers and colour palette across manually using the steps below.

**To bring your layer mappings across:**
1. Find your old `layers.chromatics3` file. It will be in the same folder you had Chromatics 3 installed in.
2. Open Chromatics 4 and go to the **Mapping** tab.
3. Click **Import** and select your `layers.chromatics3` file.

**To bring your colour palette across:**
1. Find your old `palette.chromatics3` file. It will be in the same folder you had Chromatics 3 installed in.
2. Open Chromatics 4 and go to the **Palette** tab.
3. Click **Import** and select your `palette.chromatics3` file.

 Your effects settings will need to be configured again from scratch. We apologise for the inconvenience — the rebuild was significant enough that a fully automatic migration was not possible.

## Moving Chromatics to another PC

To transfer your setup to a new computer:

1. Copy the whole `%AppData%\Chromatics\` folder from the old PC to the same location on the new one.
2. Install Chromatics 4 on the new PC using the steps above.
3. Launch Chromatics — your layers, palettes, effects, and settings will be there.

Alternatively, you can export your layers and palettes individually from inside the app using the **Export** buttons in the Mappings and Palette tabs.

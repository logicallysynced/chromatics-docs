---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/DpGqSy4CPpGNrMRyhQGc/getting-started/running-chromatics
---

# Running and Updating

## Recommended launch order

Chromatics needs Final Fantasy XIV to be running before it can read anything from the game. For the smoothest experience, open apps in this order:

1. **Final Fantasy XIV** — launch the game and reach the title screen or beyond.
2. **Chromatics** — start the app. It will connect to the game within a few seconds.
3. **Any other third-party software** — your RGB vendor's control panel, overlays, etc.

If Chromatics is already running when you start the game, it will detect FFXIV automatically. You don't have to restart anything.

## Minimising and closing

Chromatics lives in the Windows system tray (the small icons next to the clock) while it's running.

* Clicking the **red X** in the window's title bar will close Chromatics by default.
* If you'd rather have the red X minimise Chromatics to the tray instead of quitting, turn on **Settings → General → Minimise to system tray on close**.
* To fully quit Chromatics from the tray, **right-click the Chromatics icon** in the system tray and choose **Close**.
* To bring the window back after minimising, click the tray icon or right-click and choose **Show Window**.

{% hint style="info" %}
You can also set Chromatics to start minimised to the tray when Windows boots. See **Settings → General → Start Chromatics minimised to the tray** and **Start Chromatics when Windows starts**.
{% endhint %}

## Updating Chromatics

Chromatics 4 updates itself automatically. On startup, it checks for new releases and offers to install them. You don't need to download anything by hand.

### Automatic updates

When a new version is available you'll see a prompt to install it. Once you accept, Chromatics downloads the update, applies it in the background, and restarts cleanly. Your settings, layers, and palettes are untouched.

Automatic update checks can be turned off or re-enabled at any time:

* **Settings → General → Check for updates on startup**

### Beta channel

If you want to try new features and fixes before they reach the general release, you can opt in to the beta channel:

* **Settings → Advanced → Opt in to beta releases**

With this on, Chromatics checks the beta update feed as well as the stable one and installs whichever version is newest.

See [Beta Releases](beta-releases.md) for more detail on the beta programme.

### Checking manually

You can also trigger an update check yourself any time:

* **Settings → Advanced → Check for Updates**

### Portable users

If you use the portable ZIP version, you can still use in-app auto-updates. If you prefer to do it by hand, just download the newest ZIP and extract it over your existing folder. Your settings live in `%AppData%\Chromatics\`, so they won't be affected.

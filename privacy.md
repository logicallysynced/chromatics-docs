# Privacy Policy

**Last updated:** 17 May 2026

Chromatics is a free, open-source companion app for Final Fantasy XIV. This page explains exactly what Chromatics reads, what it stores, what it sends, and how to opt out of any of it.

In short: Chromatics collects nothing in normal use. The one exception is crash reporting and basic performance telemetry through Sentry, both described below. You can turn off the telemetry path entirely, and crash reports are always opt-in per event.

## What Chromatics reads from your PC

Chromatics needs to know what's happening in FFXIV to drive your lighting. To do that, it:

* Reads memory from the FFXIV process (your HP, MP, job, weather, cast progress, etc.) using the open-source [Sharlayan](https://github.com/FFXIVAPP/sharlayan) library. This is strictly **read-only** - Chromatics never writes to the game, modifies it, or injects into it.
* Listens to your Windows default audio output device when the Audio Visualizer base layer is enabled.
* Samples colours from the FFXIV game window when the Screen Capture base layer is enabled.

None of this data leaves your PC. Audio is sampled in real time and never recorded. Screen samples are reduced to colour gradients and never saved.

## What Chromatics stores on your PC

Chromatics keeps all of its configuration in `%AppData%\Chromatics\` on your local drive:

* `layers.chromatics4` - your mapped layers per device.
* `palette.chromatics4` - your colour palettes.
* `effects.chromatics4` - your Effects tab toggles.
* `settings.chromatics4` - general and advanced settings, including any Philips Hue bridge credentials and adopted-device lists for LIFX and Yeelight.

These files live on your computer only. We don't sync them, upload them, or have any access to them.

## What Chromatics sends off your PC

In normal operation, **nothing**.

Two telemetry paths exist through Sentry to help us catch crashes and performance issues. They're controlled independently and both are documented below.

### Background telemetry (opt-out)

**Default:** Enabled. Toggle off at **Settings → Advanced → Send anonymous performance and error telemetry**.

When enabled, Chromatics sends:

* Error-tier log lines only. Lower-priority logs stay on your PC.
* Anonymous performance transactions and profiling samples.
* Anonymous session counts, used to calculate crash-free release-health statistics.
* Process metrics on a 60-second heartbeat: memory usage, managed heap size, CPU percentage, GC counts, thread count.

When disabled, none of the above leaves your PC. The Sentry SDK stays loaded so the post-crash dialog below can still offer you the choice to send a report when a crash happens.

### Crash reports (opt-in per event)

Crash reports are always opt-in for each individual crash, even when background telemetry is enabled.

When Chromatics crashes, a dialog appears showing the error type, a Sentry reference ID, and an optional free-text comment box. **Nothing is sent until you click Send.** Clicking Don't Send discards the report.

A submitted crash report contains:

* The exception stack trace.
* The ~100 most recent log lines as breadcrumbs.
* The Chromatics version, your OS version, and your .NET runtime version.
* Any comment you typed yourself.

### What Chromatics never sends

We've gone out of our way to make sure none of the following ever leaves your PC, in either telemetry path:

* Your name, email address, or any other personally identifying information. The crash dialog asks only for an optional free-text comment.
* Your FFXIV character name, server, free company, or any account information.
* Your IP address.
* The contents of your screen, your keystrokes, or any input.
* File paths or settings outside of what's directly relevant to a crash.
* Your Hue bridge keys, LIFX or Yeelight device IDs, or any device credentials.

## Controlling your data

* **Opt out of background telemetry:** open **Settings → Advanced** and turn off **Send anonymous performance and error telemetry**.
* **Opt out of an individual crash report:** click **Don't Send** in the crash dialog whenever it appears.
* **Disable the crash dialog entirely:** build Chromatics from source after removing the `Sentry` package. The official builds always include Sentry so the post-crash dialog stays available.
* **Delete your local data:** close Chromatics, then delete the `%AppData%\Chromatics\` folder. Chromatics will start fresh on next launch.

## How long crash data is kept

Sentry stores submitted crash reports for up to 90 days, then deletes them automatically. We use them only to reproduce and fix bugs. We don't share them with third parties.

## Third-party services

* **[Sentry](https://sentry.io)** - error and performance monitoring. See [Sentry's privacy policy](https://sentry.io/privacy/) for details on how they handle the data Chromatics sends.
* **GitHub** (for downloads and issue tracking) and **Discord** (for community support) are governed by their own privacy policies. Chromatics doesn't share anything with either; you interact with them directly if you choose to.

## Changes to this policy

If we materially change how Chromatics handles your data, we'll update this page and flag the change in the Chromatics changelog. You can also see the full history of this file on [GitHub](https://github.com/logicallysynced/chromatics-docs/commits/main/privacy.md).

## Questions

Open an issue on [GitHub](https://github.com/logicallysynced/Chromatics/issues) or drop by our [Discord](https://discord.gg/sK47yFE).

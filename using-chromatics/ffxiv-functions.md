---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/DpGqSy4CPpGNrMRyhQGc/using-chromatics/ffxiv-functions
---

# Layer Types

This page is a reference for every layer type Chromatics 4 provides. Layers live on the [Mappings](mappings.md) tab, and each one can be attached to a base, dynamic, or effect role depending on what it does.

If you haven't yet, read [Mappings](mappings.md) first for the big picture of how layers fit together.

## Base Layers

The base layer sits under everything else. Only one is active per device at a time. Pick whichever background behaviour fits the mood you want.

<table><thead><tr><th width="210">Layer</th><th>Description</th></tr></thead><tbody>
<tr><td><strong>Static</strong></td><td>Displays a single solid colour across the entire device. Great as a clean foundation for dynamic layers to sit on top of.</td></tr>
<tr><td><strong>Reactive Weather</strong></td><td>Shows a colour (and optionally an animation) that matches the current weather in your zone. Pairs well with the <strong>Reactive Weather</strong> effect toggle on the <a href="effects.md">Effects</a> tab.</td></tr>
<tr><td><strong>Battle Stance</strong></td><td>Changes colour depending on whether your character is in combat.</td></tr>
<tr><td><strong>Job Classes</strong></td><td>Changes colour depending on your character's current job or class.</td></tr>
<tr><td><strong>Screen Capture (Beta)</strong></td><td>Samples the colours of the Final Fantasy XIV game window and spreads them across your devices — an ambient-lighting style effect that matches what's on screen.</td></tr>
<tr><td><strong>Audio Visualizer (Beta)</strong></td><td>Turns your keyboard (or any other grid-capable device) into a spectrum analyser. Reacts to your Windows audio output, so game music and sound effects drive the animation. See <a href="#audio-visualizer">below</a> for details.</td></tr>
</tbody></table>

## Dynamic Layers

Dynamic layers sit between the base layer and the effect layer. You can add as many as you like, each covering whichever keys or LEDs you choose.

<table><thead><tr><th width="240">Layer</th><th>Description</th></tr></thead><tbody>
<tr><td><strong>Highlight</strong></td><td>Lights the layer's selected keys with a highlight colour. Useful for marking a zone of your keyboard — your WASD cluster, for example.</td></tr>
<tr><td><strong>Keybinds</strong></td><td>Lights each selected key based on whether the ability bound to it is available, on cooldown, or unassigned.<br><br><em>Keyboard devices only.</em></td></tr>
<tr><td><strong>Enmity Tracker</strong></td><td>Shows your current aggro / enmity level on your target.<br><br><em>Modes: Interpolate, Fade.</em></td></tr>
<tr><td><strong>Target HP</strong></td><td>Shows your current target's HP as a bar across the selected keys.<br><br><em>Modes: Interpolate, Fade.</em></td></tr>
<tr><td><strong>Target Castbar</strong></td><td>Shows your target's cast progress in real time.<br><br><em>Modes: Interpolate, Fade.</em></td></tr>
<tr><td><strong>HP Tracker</strong></td><td>Shows your character's HP across the selected keys. Switches to the critical colour below a configurable threshold (default 20%).<br><br><em>Modes: Interpolate, Fade.</em></td></tr>
<tr><td><strong>MP Tracker</strong></td><td>Shows your character's MP, CP, or GP depending on your job.<br><br><em>Modes: Interpolate, Fade.</em></td></tr>
<tr><td><strong>Job Gauge A</strong></td><td>Your primary job gauge (for example, a tank's aggro stance gauge or a healer's lily gauge).<br><br><em>Modes: Interpolate, Fade.</em></td></tr>
<tr><td><strong>Job Gauge B</strong></td><td>A secondary job gauge if the job has one.<br><br><em>Modes: Interpolate, Fade.</em></td></tr>
<tr><td><strong>Job Gauge C</strong></td><td>A tertiary job gauge for the jobs that have three.<br><br><em>Modes: Interpolate, Fade.</em></td></tr>
<tr><td><strong>Experience Tracker</strong></td><td>Shows your current experience progress towards the next level.<br><br><em>Modes: Interpolate, Fade.</em></td></tr>
<tr><td><strong>Battle Stance</strong></td><td>Colours the selected keys based on whether you're in combat.</td></tr>
<tr><td><strong>Castbar</strong></td><td>Shows your own cast progress in real time.<br><br><em>Modes: Interpolate, Fade.</em></td></tr>
<tr><td><strong>Job Classes Highlight</strong></td><td>Colours the selected keys based on your current job or class.</td></tr>
<tr><td><strong>Reactive Weather Highlight</strong></td><td>Colours the selected keys based on the current weather in your zone.</td></tr>
</tbody></table>

## Effect Layer

The effect layer is the top layer of every device. It's used by flash-style effects that need to override everything else for a moment — the Duty Finder Bell, Damage Flash, and so on.

You don't assign a function to the effect layer directly; instead you turn the corresponding effects on or off on the [Effects](effects.md) tab.

## Audio Visualizer

The Audio Visualizer is a **base layer**, not an effect. To turn it on, open the Mappings tab, set your device's base layer type to **Audio Visualizer (Beta)**, and you're done.

It works by listening to whatever is currently playing through your Windows default audio output — so if FFXIV audio goes through that device, the music and sound effects drive the animation. Background music in a dungeon will light up your keyboard rhythmically; a loud boss ability will pulse the display.

Colours for the visualizer live in the **Audio Visualizer** category in the [Palette](palettes.md) tab:

* **Base** — the dim background colour.
* **Low** — bass frequencies.
* **Mid** — mid frequencies.
* **High** — treble frequencies.

{% hint style="info" %}
Because the visualizer uses the Windows default output, any audio playing on your PC affects it — not just FFXIV. A YouTube video or Discord call will also move the bars.
{% endhint %}

## Screen Capture (Beta)

Screen Capture is another base layer. When active, Chromatics samples colours from the FFXIV game window and paints a matching ambient gradient across your devices — a soft, always-on-theme backdrop that responds to what's on screen.

Screen Capture only samples the FFXIV window, so other applications won't affect it.

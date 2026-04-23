---
metaLinks:
  alternates:
    - https://app.gitbook.com/s/DpGqSy4CPpGNrMRyhQGc/using-chromatics/settings
---

# Settings

<figure><img src="../.gitbook/assets/Chromatics4_SettingsLight.png" alt=""><figcaption></figcaption></figure>

## General Settings

### Use Local Cache

By default, Chromatics automatically downloads the necessary reference data to read Final Fantasy XIV data from an online database. To prevent this functionality and use locally cached reference data, select Use Local Cache.

**Default:** False

### Run on Windows Start

If this option is selected, Chromatics will automatically start when you first boot windows.

**Default:** False

### Minimise to Tray

If this option is selected, Chromatics will minimise to the system tray if closed using the red X. If this option is disabled, Chromatics will exit when closed using the red X.

**Default:** False

### Minimise to Tray on Startup

When Chromatics starts up, it will start minimised to the system tray.

**Default:** False

### Check for Updates

When Chromatics starts up, it will check for new versions of Chromatics.

**Default:** True

### Reset Chromatics

This option will reset Chromatics back to its default state by removing all config files in the installation directory. You will need to restart Chromatics for this to take effect.

### Clear Cache

Use this button to clear the reference data stored with Chromatics. You will need to restart Chromatics for this to take effect.

### Global Device Controls

{% hint style="warning" %}
This option is currently not available in the current Chromatics 3 beta.
{% endhint %}

This option limits all device colours by a certain brightness.



## Advanced Settings

Some settings are not configurable in the UI. To change these settings you need to manually edit the settings.chromatics3 file in your installation directory.

<table><thead><tr><th width="317">Setting</th><th>Description</th></tr></thead><tbody><tr><td>rgbRefreshRate</td><td>Changes the refresh rate of the RGB.NET primary surface. <em>It is highly recommended you don't make this lower than 0.05.</em><br><em><strong>Default:</strong> 0.05</em><br><em><strong>Values:</strong> 0.0-100.0</em><br><br><em>Requires restarting Chromatics to take effect.</em></td></tr><tr><td>keyboardLayout</td><td><p>Sets the default keyboard layout of Chromatics.<br><em><strong>Default:</strong> 1</em><br><em><strong>Values:</strong> (integer)</em><br></p><p><em>1: QWERTY</em><br><em>2: QWERTZ</em><br><em>3: AZERTY</em></p></td></tr><tr><td>criticalHpPercentage</td><td>Changes the threshold percentage for changing the HP tracker to the critical colour.<br><em><strong>Default:</strong> 20.0</em><br><em><strong>Values:</strong> 0.0-100.0</em></td></tr><tr><td>deviceLogitechEnabled</td><td><p>Toggle the loading of the Logitech library.<br><em><strong>Default:</strong> true</em></p><p><em><strong>Values:</strong> true/false</em><br><br><em>Requires restarting Chromatics to take effect.</em></p></td></tr><tr><td>deviceCorsairEnabled</td><td><p>Toggle the loading of the Corsair library.<br><em><strong>Default:</strong> true</em></p><p><em><strong>Values:</strong> true/false</em><br><br><em>Requires restarting Chromatics to take effect.</em></p></td></tr><tr><td>deviceCoolermasterEnabled</td><td><p>Toggle the loading of the Coolermaster library.<br><em><strong>Default:</strong> true</em></p><p><em><strong>Values:</strong> true/false</em><br><br><em>Requires restarting Chromatics to take effect.</em></p></td></tr><tr><td>deviceRazerEnabled</td><td><p>Toggle the loading of the Razer library.<br><em><strong>Default:</strong> true</em></p><p><em><strong>Values:</strong> true/false</em><br><br><em>Requires restarting Chromatics to take effect.</em></p></td></tr><tr><td>deviceAsusEnabled</td><td><p>Toggle the loading of the Asus library.<br><em><strong>Default:</strong> true</em></p><p><em><strong>Values:</strong> true/false</em><br><br><em>Requires restarting Chromatics to take effect.</em></p></td></tr><tr><td>deviceMsiEnabled</td><td><p>Toggle the loading of the MSI library.<br><em><strong>Default:</strong> true</em></p><p><em><strong>Values:</strong> true/false</em><br><br><em>Requires restarting Chromatics to take effect.</em></p></td></tr><tr><td>deviceSteelseriesEnabled</td><td><p>Toggle the loading of the SteelSeries library.<br><em><strong>Default:</strong> true</em></p><p><em><strong>Values:</strong> true/false</em><br><br><em>Requires restarting Chromatics to take effect.</em></p></td></tr><tr><td>deviceWootingEnabled</td><td><p>Toggle the loading of the Wooting library.<br><em><strong>Default:</strong> true</em></p><p><em><strong>Values:</strong> true/false</em><br><br><em>Requires restarting Chromatics to take effect.</em></p></td></tr><tr><td>deviceNovationEnabled</td><td><p>Toggle the loading of the Novation library.<br><em><strong>Default:</strong> true</em></p><p><em><strong>Values:</strong> true/false</em><br><br><em>Requires restarting Chromatics to take effect.</em></p></td></tr><tr><td>deviceHueEnabled</td><td><p>Toggle the loading of the Philips HUE library.<br><em><strong>Default:</strong> false</em></p><p><em><strong>Values:</strong> true/false</em><br><br><em>Requires restarting Chromatics to take effect.</em></p></td></tr><tr><td>deviceHueBridgeIP</td><td><p>Sets the IP address of the Philips HUE bridge manually.<br><em><strong>Default:</strong> 127.0.0.1</em></p><p><em><strong>Values:</strong> IP Address</em><br><br><em>Automatically set by app when set to default value.</em></p></td></tr><tr><td>deviceHueBridgeKey</td><td><p>Sets the Bridge client key of the Philips HUE bridge manually.<br><em><strong>Default:</strong> N/A</em></p><p><em><strong>Values:</strong> alphanumeric</em><br><br><em>Automatically set by app when set to default value.</em></p></td></tr><tr><td>deviceHueBridgeStreamingKey</td><td><p>Sets the Bridge streaming key of the Philips HUE bridge manually.<br><em><strong>Default:</strong> N/A</em></p><p><em><strong>Values:</strong> alphanumeric</em><br><br><em>Automatically set by app when set to default value.</em></p></td></tr></tbody></table>


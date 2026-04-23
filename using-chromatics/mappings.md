---
metaLinks:
  alternates:
    - https://app.gitbook.com/s/DpGqSy4CPpGNrMRyhQGc/using-chromatics/mappings
---

# Mappings

The mappings page allows you to setup the lighting exactly the way you like. A default profile is loaded when you launch Chromatics for the first time.

Chromatics 3 uses the concept of layers, you can setup multiple layers per device and map those layers to specific keys (or LEDs) on a device.



## Layer Types

#### Base Layer

The base layer is always set as the lowest layer for each device type, it contains all keys/LEDs in a device. You can use this type of layer to set a solid colour over the entire device to build upon. This is a static layer that you cannot move, remove or add a new base layer.

#### Dynamic Layer

Dynamic Layers allow you to build out certain looks on your devices. There are many [types](ffxiv-functions.md) of dynamic layers and you can add/remove specific keys from a dynamic layer.

#### Effect Layer

The effect layer contains all keys/LEDs of a device, and also can't be moved or removed. Most effects operate on this layer which is above all other layers.



## Mappings

<figure><img src="../.gitbook/assets/Chromatics3_MappingsScreen_Diagram (1).png" alt=""><figcaption></figcaption></figure>

<table><thead><tr><th width="106.33333333333331"></th><th></th></tr></thead><tbody><tr><td><strong>A</strong></td><td><strong>Device Selection</strong><br>Changes the currently displayed device type.</td></tr><tr><td><strong>B</strong></td><td><strong>Import Layers</strong><br>Imports a layer file from your PC. This will overwrite all existing layers for all devices you have setup.</td></tr><tr><td><strong>C</strong></td><td><strong>Export Layers</strong><br>Exports your current layer setup to a file on your PC.</td></tr><tr><td><strong>D</strong></td><td><strong>Preview Layers</strong><br>Display your current layers on your devices.</td></tr><tr><td><strong>E</strong></td><td><strong>Layer Type to Add</strong><br>Change what type of layer to add. Currently this is only set to Dynamic Layer.</td></tr><tr><td><strong>F</strong></td><td><strong>Add Layer</strong><br>Add a new layer to the list, this will be added above the base layer. You cannot add a base or effect layer.</td></tr><tr><td><strong>G</strong></td><td><strong>Layer ID</strong><br>The layer ID for each layer, which also indicates the stack order of the layer. A layer with a higher ID is always on top of a layer with a lower ID.<br><br>You can drag and drop layers to change their order, but you cannot change the order of the base or effect layer.</td></tr><tr><td><strong>H</strong></td><td><strong>Layer Type</strong><br>The layer type of the selected layer, either base, dynamic or effect layer.</td></tr><tr><td><strong>I</strong></td><td><strong>Layer Function</strong><br>The function for the layer, which indicates the what type of FFXIV integration is attached to that layer. For a list of available functions, see <a href="ffxiv-functions.md">FFXIV Functions</a>.</td></tr><tr><td><strong>J</strong></td><td><strong>Layer Enable</strong><br>Enable/disabled this layer.</td></tr><tr><td><strong>K</strong></td><td><strong>Edit Layer</strong><br>Edit the keys assigned to the layer.</td></tr><tr><td><strong>L</strong></td><td><strong>Delete/Copy Layer</strong><br>Deletes the selected layer.<br>If you hold SHIFT, this will change to copy and allow you to duplicate the layer.</td></tr><tr><td><strong>M</strong></td><td><strong>Enable Bleeding</strong><br>This button determines whether a layer can bleed through to lower layers when the current layer has nothing to display. When set to enabled, the layer can bleed through, and when set to disabled, the layer will not bleed through to lower layers.</td></tr><tr><td><strong>N</strong></td><td><strong>Layer Mode</strong><br>On some layers, there are different modes available depending on the type of device.</td></tr><tr><td><strong>O</strong></td><td><strong>Undo</strong><br>When editing a layer, you can undo any changes you have made using this button.</td></tr><tr><td><strong>P</strong></td><td><strong>Reverse</strong><br>When editing a layer, you can reverse the selected keys using this button.</td></tr><tr><td><strong>Q</strong></td><td><strong>Clear</strong><br>When editing a layer, you can clear all selected keys using this button. When clearing a layer, you will exit editing mode.</td></tr><tr><td><strong>R</strong></td><td><strong>Key Selection</strong><br>When editing a layer, you can select which keys you want attached to the layer.</td></tr></tbody></table>



## Keyboard Layouts

Currently only one keyboard layout en-us is available on the mapping tab. This is a QWERTY keyboard so if you use a different layout, such as AZERTY you will need to remap keys accordingly.



## Layer Bleeding

By default, colour palettes for each layer function have a negative colour. This means that when this layer has nothing to display it will display the negative colour, usually black.

For example, if you have the dynamic layer HP Tracker assigned to a set of keys and you were currently at 50% HP, half of your keys will be the HP tracker colour palette (default green) and half of your keys will be the negative color (default black).

When bleeding is enabled for a layer, instead of showing the negative colour, it becomes transparent instead allowing lower layers to _bleed_ through.



## Layer Modes

Certain dynamic layers support changing the mode of the layer.

### Interpolate

When set to interpolate, the lighting of the layer's selected keys will be spread across those keys. This can give the effect of a bar across your device (e.g. health bar).

### Fade

When set to fade, the lighting of the layer's selected keys will all fade between the two colour's. This mode is good for non-keyboard devices which don't necessarily have consecutive key layouts.

---
title: Translating the TU40 v3 Keyboard Software
excerpt: ":japanese_ogre: A cool 2.4 GHz ortholinear keyboard imprisoned in closed-source software."
tags: HIDs
header:
    header: /assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/tu40-photo.jpg
    teaser: /assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/tu40-photo.jpg
    og_image: /assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/tu40-photo.jpg
    overlay_image: /assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/tu40-photo.jpg
---
As a diehard ortholinear keyboard user with a proclivity for 40-something %s, I wanted to build this TU40 v3 keyboard that I saw on [AliExpress](https://www.aliexpress.com/item/3256802932623629.html?gatewayAdapt=4itemAdapt).  It’s a little different from what I’m used to in that the ortholinear version of the PCB supports only 2 x 2u spacebars, but I figure I can code up some stuff so it makes sense. The main draw of this keyboard is that it features 2.4 GHz connectivity, which is hard to find on a custom programmable keyboard, because the 2.4 GHz connectivity protocols are usually proprietary (as it remains even on this keyboard). 

{% include figure image_path="/assets/images/posts//2022-07-22-translating-the-TU40-v3-keyboard-software/stock-photo.png" alt="" caption="An image of the two different TU40 v3 supported layouts: a staggered alyout and an ortholinear layout. Ortholinear layout all the way!" %}

That being said, this keyboard doesn’t actually use QMK or some other common software for reprogramming keyboard firmware. Rather, it uses some free but proprietary software that is somewhat difficult to navigate. In my opinion, the software is clearly a wrapper around [QMK](https://qmk.fm/).  Instructions for navigating the software can be found on [this GitBook](https://tustation.gitbook.io/tuusermanual/shi-yong/chu-shi-qu-dong?spm=a2g0s.imconversation.0.0.3b013e5fw6txHG), which is in Chinese, but fortunately, Google Translate has really improved. I’ll screenshoot the English translations onto this article, for ease of use. 

## Download and Launch the Driver
The [GitBook link](https://tustation.gitbook.io/tuusermanual/shi-yong/chu-shi-qu-dong?spm=a2g0s.imconversation.0.0.3b013e5fw6txHG) above links the software for reprogramming the keyboard. Links for both Mac and Windows-compatible software versions are shown, but as of May 26, 2022, only the Windows version appears to work (V2.7.3 WIN platform). 

Plug in the keyboard and then start up the software. You should be greeted with a window like so:

{% include figure image_path="/assets/images/posts//2022-07-22-translating-the-TU40-v3-keyboard-software/start-up-menu.png" alt="" caption="The left button means “open”. The centre button means “refresh”. The right button means “example”. The text in blue says “Unable to find equipment?”." %}

{% include figure image_path="/assets/images/posts//2022-07-22-translating-the-TU40-v3-keyboard-software/dev-manager.gif" alt="" caption="A `.gif` from the official GitBook that demonstrates the launch of the keymap programmer. " %}

## Modifying the Key Values
We can control the exact keymap of our keyboard. To do so, we simply need to select the key we are interested in modifying on the keyboard image, and then select the value we want to map that key to, from the below menu. The keymapping menu supports all sorts of things, and is divided up into 8 main categories:

1. Basic Keys
2. Layer Control
3. Light Control Keys
4. Multimedia Keys
5. Combination Keys
6. 2-in-1 Keys
7. Macro Keys
8. Function Keys

A key can have no value assigned if the 🚫 icon is selected. 

The following images show all the various values that can be assigned to the keyboard’s keys:

### Basic Keys

![](/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/keymap_english_translation_0a.png)

### Layer Control Keys

See [Layer Control](#layer-control) for more details.
![](/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/keymap_english_translation_0b.png)
![](/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/layer-control-keys.png)

### Light Control Keys

See [Backlight](#backlight) for more information about backlight control. 

![](/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/keymap_english_translation_0c.png)

{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/bottom-light-control.png" alt="" caption="Bottom Light Control"%}

### Multimedia Keys

![](/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/keymap_english_translation_0d.png)

![](/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/multimedia-keys.png)

### Combination Keys

See [Combination Keys](#combination-keys) for more details. 

![](/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/keymap_english_translation_0e.png)

### 2-in-1 Keys

See [2-in-1](#2-in-1-key) for more details.

![](/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/keymap_english_translation_0f.png)

### Macro Keys

See [Macro Keys](#macro-keys-1) for more details.

![](/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/keymap_english_translation_0g.png)

### Function Keys

These keys are used to operate the wireless module. See the “Wireless” section for more details.

![](/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/keymap_english_translation_0h.png)


## Some Other Basic Functions
The bottom left menu provides some key operations for working with the keymap:

![](/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/basic-menu.png)

- The ⬇️ icon refers to “download” and it writes the current configuration to the keyboard.
- The ⬆️ icon refers to “upload” and it reads the configuration from the keyboard.
- The 📂 icon refers to “load” and it loads a a configuration from a local file.
- The 💾 icon refers to “save” and it saves the current configuration to a local file.
- The 🔄 icon refers to “restore” and it restores the selected layer to its default configuration.
- The 🚫 icon refers to “disable” and it disables the selected key.

## Keymap and Layer Control
### Keymap Control
The TU40 can store up to 4 keymaps. These keymaps are not layers, but keymaps. That’s right, the TU40 can support 4 whole _keymaps_. One use case for storing multiple keymaps might be for working with different operating systems. Each keymap can encode 4 layers. A keymap can be accessed by `KM_`, where `_` is the keymap number. So we can have a button load up keymap 2, by having it encode `KM2`. It’s a good idea to always have the ability to move to the other keymaps, when on any given keymap. We don’t want to be trapped on a particular keymap.
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/settings_0.png" alt="" caption="The TU40 can store up to 4 keymaps, and each keymap can store up to 4 layers."%}

### Layer Control
The TU40 can store up to 4 layers, for each keymap. Layer 1 is the bottom layer, and is the default layer. `LM2` - `LM4` activate the designated layer _momentarily_. They activate only while the key is held down. As soon as the the key is let go, the target layer is inactivated. If a key on the target layer does not a value assigned, then the key from the origin layer will simply be used instead. For example:
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/eg-layer-1.png" alt="" caption="Layer 1."%}
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/eg-layer-2.png" alt="" caption="Layer 2."%}
If we hit `LM2` on Layer 1, as designated in green, and then select the valueless red key on Layer 2, then the corresponding key from the origin layer, Layer 1, will be activated instead. In this case, the output will be `1`.  

In contrast, the the `LT2` - `LT4` values toggle the designated layer. They activate the layer, until they are hit again. For example, if we are on layer 1 and we hit `LT2`, layer 2 will be activated. In order to get back to layer 1, we are going to have to hit `LT2` again, provided that `LT2` is on layer 2. In other words, we should always encode the origin layer at the target layer, or else, we will be stuck at the target layer. 

:bulb: **FYI** :bulb:: A simple trick to make sure you’re not stuck on a layer, after hitting_ `LT_`_, is to make the target layer have no value assigned to the key that had the_ `LT_` _value at the origin layer.
{: .notice--info}

### Key Combination
The combination key menu lets the user combine a target key with the keys that are next to the check boxes shown below:
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/keymap_english_translation_0e.png" alt="" caption="The Key Combination menu page."%}

For example, one can select the `delete` key, and then also check off `LCtrl` and `LAlt` to result in a key combination that is equivalent to `ctrl` + `alt` + `delete`. To enter a key combination do as demonstrated in the below .gif: 
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/set-combo-key.gif" alt="" caption="A demo."%}

### 2-in-1 Key
The 2-in-1 key menu lets the user output different keys based on whether the user does a short or a long press. It’s equivalent to “tap-hold” from [QMK](https://qmk.fm/). 
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/keymap_english_translation_0f.png" alt="" caption="The 2-in-1 Key menu page."%}
A short press is defined as a keypress that's released within 300 ms, where a long press is defined as a keypress that's released not within 300 ms. Unfortunately, I can't find a way of changing this parameter. In QMK, the tap-hold boundary is defined by `TAPPING_TERM` in the `config.h`. 
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/2-in-1.gif" alt="" caption="A demo."%}

### Macro Keys
Macro keys can realize a series of key operations preset by one key output to improve input efficiency. They are set up across two menus:
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/keymap_english_translation_0g.png" alt="" caption="The menu for mapping macros onto the keyboard."%}
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/settings_2.png" alt="" caption="The menu for specifying macro definitions."%}

The TU40 can store up to 32 macro definitions, and each macro can support up to 120 actions. There are three types of macro actions: presses, releases, and delays. 

To map a key with a a macro value, perform the same process as any key-value mapping process. E.g. select the key location and then select `M_`, e.g. `M1` for macro 1. 

To write a macro definition, switch to the macro definition menu. The macro definition menu gives us the option to record the actual times taken to perform the macro, via the “recording timer” checkbox. That is, it’ll record the delays between key presses. Otherwise, if the recording timer box is not ticked, it will record only the actual key presses and releases. To start recording the macro click the “start recording” button., and enter the preset key operation sequence on the keyboard. To stop recording the macro, click the “stop recording” button. Click the “write macro” button to write the recorded macro sequence to the previously selected macro value, e.g. `M1`. 
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/set-macro-key.gif" alt="" caption="A demo."%}

## Keyboard Updates
To manage the keyboard firmware version, or read the keyboard’s serial number, go to the “General Settings” page. 
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/settings_1.png" alt="" caption="Menu for updating the keyboard firmware and reading the keyboard’s serial number."%}
To get the factory serial number of the keyboard, click the “read keyboard SN” button. If the reading is successful, it’ll be displayed on the menu’s text box. 
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/keyboard-sn.gif" alt="" caption="Demo of getting the keyboard’s serial number."%}
To get the keyboard’s current firmware version, click the “get keyboard master firmware version”. To update the keyboard’s firmware to the latest version, click the “get the latest firmware version” button. 
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/keyboard-version.gif" alt="" caption=""%}

## General Functions
The keyboard has some additional ‘general’ settings. 
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/settings_1b.png" alt="" caption="The menu page for 'general' settings."%}

### 6KRO vs NKRO
The keyboard can use one of the following key-press protocols:

- 6KRO: Is limited by the USB HID protocol, and supports the pressing of up to 6 keys and 4 modifier keys (`ctrl` , `alt` , `win`, `shift`).
- NKRO: uses a non-standard USB HID protocol to output all pressed keys.  This mode is not compatible with some BIOS systems.

Select the `Read` button on the left hand side to figure out whether the keyboard is using 6KRO or NKRO. The result will show up in green on the left hand corner. To write the desired mode, select the mode of choice and then hit the `Set up` button to the left. The keyboard must then restart. If the keyboard is wired, simply re-plug and unplug the USB cable. If the keyboard is in wireless mode, press the switch on the PCB to turn the keyboard off, and then press the switch again to turn it back on.

### Sleep
The TU40 has an automatic sleep function, in order to reduce the keyboard’s power consumption. We can set the time, in *seconds*, that must pass before the keyboard falls asleep. By default, the inactivity time before sleeping is 180 s. 

You can also specify what will trigger the keyboard to wake up. Either a single `ESC` press, or any key press can wake up the keyboard from sleep mode. Hit `Read` under the “Wake up mode” heading to figure out what currently triggers the keyboard to wake. Hit `Set up` under the “Wake up mode” heading to write the method that triggers the keyboard to wake. 

The TU40 also has a button that will automatically make the keyboard fall asleep:

![](/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/sleep.png)

## Indicator Lights
We can assign which state will activate an indicator light. There are only 5 indicator lights on this keyboard. 
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/settings_1d.png" alt="" caption="The menu that specifies the meaning of the indicator light."%}
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/indicator-spots.png" alt="" caption="The five places on the keyboard for which we can sign indicators. I’ve chosen to assign indicator LEDs to states BLE1-3, 2.4 G, and Layer 4."%}
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/indicator-legend.png" alt="" caption="“Arrangement” here refers to the keymap."%}

To map an indicator light’s state to a key’s LED, simply select the key, the desired state for representation, and then hit the `set up` button. 
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/write-led.gif" alt="" caption="Write demo."%}

Conversely, we can also read the keyboard’s current indicator light configuration. We just need hit the `read` button. 
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/read-led.gif" alt="" caption="Read demo."%}

## Backlight
The TU40 backlight is monochrome and supports three light modes: 
- **Always on:** Supports 5 levels of brightness
- **Breathing:** Supports 3 levels of breathing rates
- **Button:** This mode has two sub-modes: a) the more the button mode is hit, the brighter the keyboard becomes; b) the more the button is hit, the dimmer the keyboard becomes.

A more detailed table below shows the function of each light-related key value when in a given mode:

| key value  | disabled              | alwayys on mode          | breathing pattern mode   | button mode                 |
| ---------- | --------------------- | ------------------------ | ------------------------ | --------------------------- |
| `ONOFFLED` | Turn on the backlight | Turn off the backlight   | Turn off the backlight   | Turn off the backlight      |
| `NEXTLED`  | -                     | Switch to breathing mode | Switch to key mode       | -                           |
| `PREVLED`  | -                     | -                        | Switch to always on mode | Switch to breathing mode    |
| `F++LED`   | -                     | Increase brightness      | Breathe faster           | Toggle get brighter submode |
| `F--LED`   | -                     | Reduce brightness        | Slow down breathing      | Toggle get brighter submode |
| `H++LED`   | -                     | -                        | -                        | -                           |
| `H--LED`   | -                     | -                        | -                        | -                           |
| `S++LED`   | -                     | -                        | -                        | -                           |
| `S--LED`   | -                     | -                        | -                        | -                           |
| `B++LED`   | -                     | -                        | -                        | -                           |
| `B--LED`   | -                     | -                        | -                        | -                           |

## Wireless

The TU40 has up to three different wireless modes: 2.4 GHz, Bluetooth, and Unifying Bluetooth. 
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/wireless.png" alt="" caption=""%}
The supporting wireless modules have been installed on the PCB from the factory. These modules are shown below:
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/wireless-hardware.png" alt="" caption=""%}
To figure out which wireless modes are being used, click the `read permission` button for the wireless mode of interest. 
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/settings_1c.png" alt="" caption="The menu for wireless connections."%}
I am unclear about what the `write permission` buttons mean. 

## Battery
The TU40 does not have reverse voltage protection, so make sure the battery is connected with the correct polarity. Purchasing batteries from a different vendor, such a Amazon, might mean that you have to manually reverse the polarity of the battery. 

The TU40 PCB has a charging board located next to the battery holder (it’s the top left side of the keyboard). When the red light is on, the battery is charging.
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/red-light.png" alt="" caption=""%}

When the blue light is on, the battery is fully charged.
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/blue-light.png" alt="" caption=""%}

## 2.4 GHz
2.4 G is only available on TU keyboards that possess the 2.4 G wireless module. Enabling the 2.4 G mode requires the keyboard to be unplugged. Otherwise, the keyboard will operate in wired mode.  2.4 G-capable keyboards will have come with a USB adapter that the keyboard was already paired with at the factory.  If for some reason, the USB adapter is not paired with the keyboard, there are two ways of pairing the keyboard with 2.4 G:

1. With removing the battery
    1. Unplug the keyboard data cable, remove the keyboard battery, remove the USB adapter, and keep the PCB switch on.
    2. Insert the keyboard data cable, open the driver software, and click `eliminate pairings` under the 2.4 G module permission management on the wireless menu. The status bar on the bottom left corner will pop up to show that the pairing was successfully cleared. 
    3. Unplug the keyboard data cable, insert the USB adapter into the computer, install the battery, and click any button on the keyboard until the computer displays a button trigger to complete the pairing. 
    
2. Without removing the battery
    1. Unplug the keyboard data cable, remove the USB adapter, keep the PCB switch on, and do not bother removing the battery.
    2. Insert the keyboard data cable, open the driver software, and click `eliminate pairings` on the wireless menu page. 
    3. Unplug the keyboard data cable, turn off the PCB switch, insert the USB adapter into the computer, turn on the PCB switch, and then click any key on the keyboard until the computer displays a key trigger to complete the pairing.

## Bluetooth
The Bluetooth section applies to the Bluetooth version of the wireless keyboard. Bluetooth connection requires the keyboard to be unplugged from the computer. Otherwise, the keyboard will function in wired mode. There are two indicators next to the Bluetooth module, one red and one blue. Their meanings are as follows:
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/bluetooth-status.png" alt="" caption=""%}
If the keyboard is in the broadcast state and does not receive a connection request within 180 seconds, it will automatically enter the sleep state. If the keyboard is in the reconnect state for 30 seconds and fails to connect to the host, it will automatically enter the sleep state. If the keyboard is in sleep state, press the default `ESC` button to exit the sleep state, and the keyboard will automatically enter either the broadcast state or the connection state, according to the last pairing information. 

The Bluetooth version of the TU40 can store the information of up to 3 host devices, and can switch between these devices. The driver software provides key values for switching between the 3 Bluetooth host devices:
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/bluetooth-symbols.png" alt="" caption=""%}
Click the desired Bluetooth device button to switch to the desired host device. If the desired host device is not already bound to the keyboard, the keyboard will enter the broadcast state. Otherwise, it will enter the reconnect state. 

To pair a new device, press and hold a key with the Bluetooth value, until the red light flashes slowly. It will force the corresponding channel of the keyboard to enter the broadcast state, and the new device will be paired once the host device agrees to the connection. 

If the host device has been connected to the keyboard before, and still has the keyboard pairing information, but the keyboard has since deleted the host device information, the keyboard and host device will not be able to pair. In these conditions, the host device must delete the keyboard pairing information, in order to connect successfully.

## Unifying Bluetooth
:bulb: **FYI** :bulb: A simple trick to make sure you’re not stuck on a layer, after hitting_ `LT_`_, is to make the target layer have no value assigned to the key that had the_ `LT_` _value at the origin layer.
{: .notice--info}

The Unifying Bluetooth section applies to the Unifying Bluetooth version of the keyboard. Its indicator light meanings are not too different from the regular Bluetooth keyboard’s indicator lights:
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/unifying-bluetooth.png" alt="" caption=""%}
Like the Bluetooth version of the keyboard, if the keyboard is in the broadcast state and does not receive a connection request within 180 seconds, it will automatically enter the sleep state. If the keyboard is in the reconnect state for 30 seconds and fails to connect to the host, it will automatically enter the sleep state. If the keyboard is in sleep state, press the default ESC button to exit the sleep state, and the keyboard will automatically enter either the broadcast state or the connection state, according to the last pairing information. 

Like the Bluetooth version of the keyboard, the Unifying Bluetooth version of the TU40 can store the information of up to 3 host devices, and can switch between these devices. The driver software provides key values for switching between the 3 Bluetooth host devices:
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/bluetooth-symbols.png" alt="" caption=""%}
Click the desired Bluetooth device button to switch to the desired host device. If the desired host device is not already bound to the keyboard, the keyboard will enter the broadcast state. Otherwise, it will enter the reconnect state. 

To pair a new device, press and hold a key with the Bluetooth value, until the red light flashes slowly. It will force the corresponding channel of the keyboard to enter the broadcast state, and the new device will be paired once the host device agrees to the connection. 

If the host device has been connected to the keyboard before, and still has the keyboard pairing information, but the keyboard has since deleted the host device information, the keyboard and host device will not be able to pair. In these conditions, the host device must delete the keyboard pairing information, in order to connect successfully.

### Setting up Unifying Bluetooth
Setting up Unifying Bluetooth requires downloading software. I haven't actually tried the software myself, because my keyboard is regular Bluetooth, and not Unifying Bluetooth.

Press and hold the `unifying` button for 5+ seconds, until the indicator light on the keyboard enters the broadcasting state (slow blue flashes). Then, open the Unifying Bluetooth pairing tool, and insert the Union adapter. Then click the `advanced` button. Select the Unifying receiver of interest, click the `pair new device` button on the right, and the keyboard should automatically connect. If the pairing attempt fails, check if the keyboard went to sleep because the broadcast timed out. 
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/unifying-pair.gif" alt="" caption="A demo."%}
## My Personal Keymap
As of 2022-06-07, my keymap is as follows:
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/keymap-layer-1.png" alt="" caption="**Layer 1**. The `play`/`pause` key activates `LM4`, when it’s held down. The left `space` activates `LM3` when it’s held down. The right space activates `LM2` when it’s held down. The `enter` key activates the right `shift` when it’s held down. ."%}
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/keymap-layer-2.png" alt="" caption="**Layer 2**. The key above the right spacebar, towards the right side, activates the Apple screenshot command (`cmd` + `shift` + `4` )."%}
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/keymap-layer-3.png" alt="" caption="**Layer 3**. The top row keys in italics activates the shifted symbols. So `~`, `!`, `@` … `)`. The italicized keys on the second row (from the top) also activates the shifted symbols. So `-`, `=`, `[`, `]`, and `\`. The italicized key on the third row is still the Apple screenshot command (`cmd` + `shift` + `4` ), like it is for Layer 2."%}
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/keymap-layer-4.png" alt="" caption="**Layer 4**. I keep my utilities here.  For whatever reason, `BLE1` connection doesn’t work for me, so I took it off."%}
{% include figure image_path="/assets/images/posts/2022-07-22-translating-the-TU40-v3-keyboard-software/keymap-layer-5.png" alt="" caption="My indicator lights and states. `BLE1` connection doesn’t seem to work for me, so I took it off. I currently use Device 2 as my iPad, and Device 3 as my Macbook Pro."%}
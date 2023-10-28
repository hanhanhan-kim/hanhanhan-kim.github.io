---
tags: 
    - HIDs
    - Tracking
excerpt: "A running record of my many keyboards."
---
I own a lot of 'weird' keyboards. One could argue that it's my strange addiction. I also like documenting things. I thought that it might be fun for me to share a running catalog of my keyboard builds. I'll share the keyboard's specs, any mods I've done, and the keymap I'm using. I'll try and update this post as I make changes to my build specs and keymaps, and sell and buy things. 

__*Note about keymap legending:*__ I make all the graphical representations of my keymaps on [Keyboard Layout Editor](http://www.keyboard-layout-editor.com/#/) (KLE).  In general, I use the following encoding:
- Black characters are _base_ layer keys.
- <span style="color:#458588">Blue (#458588)</span> characters are _lower_ layer keys.
- <span style="color:#cc241d">Red (#cc241d)</span> characters are _raise_ layer keys.
- <span style="color:#98971a">Green (#98971a)</span> characters are _adjust_ layer keys (i.e. _lower_ + _raise_), and often encode utilities. 
- <span style="color:#d79921">Orange (#d79921)</span> characters are _navigation_ layer keys
- <span style="color:#b16286">Purple (#b16286)</span> characters are _media_ layer keys, if media keys do not fit on some other layer, e.g. for the Corne keyboard.
- Characters written on the front edge of the keycaps are keys that are executed only upon holding down the keypress, such as [homerow mods](https://precondition.github.io/home-row-mods). 

For those who are curious about layers, ortholinearity, and homerow mods, I might write a brief blog post about the topics later. 

## Ortholinear Mono-Rectangles

### Void 40
My first mechanical keyboard, as well as my first 40% keyboard, and ortholinear keyboard. I thought the [Void 40](https://victorlucachi.ro/projects/void40/) would be a fun weekend project and talking piece, and that I'd never actually use the board. Once I finished building it, however, I started typing on it. Much to my surprise, I found the compact board to be incredibly comfortable. No more stretching my fingers out to reach numbers and symbols, and I never had to move my wrists, except when reaching for the mouse. I also learned that I hit the "b" key with my right hand, because on a traditional staggered keyboard, the "b" is smack dab in the middle, and I'm right hand-dominant. Apparently, a refined individual is supposed to hit the "b" with the left hand though, and the ortholinearity of the Void 40 emphasized that notion. So, the board encouraged better typing habits. 

{% include figure image_path="/assets/images/posts/2022-07-23-my-keyboards/keymaps/void40.png" alt="" caption="QMK, wired, + rotary encoder" %}

Keycaps are TODO. 
Plate is TODO.
Switches are TODO.
Mounting style is TODO. 

My QMK-powered firmware is [here](https://github.com/hanhanhan-kim/qmk_firmware/tree/master/keyboards/handwired/void40). TODO UPDATE THIS LINK

&mu;c: ATMmega 32U4 on a [Sparkfun Qwiic Pro Micro USB-C](https://www.digikey.com/en/products/detail/sparkfun-electronics/DEV-15795/11594572) breakout board.

Keymap updated 2023/10/15.

### Planck
TODO

{% include figure image_path="/assets/images/posts/2022-07-23-my-keyboards/keymaps/planck.png" alt="" caption="QMK, wired, + rotary encoder, + RGB, + music (e.g. MIDI)" %}

Keycaps are TODO. 

My QMK-powered firmware is [here](https://github.com/hanhanhan-kim/qmk_firmware/tree/master/keyboards/planck/keymaps/hanhanhan-kim). TODO UPDATE THIS LINK

&mu;c: ARM STM32 integrated into the main PCB. homero

Keymap updated 2023/10/15.

### Bloid 40
TODO

{% include figure image_path="/assets/images/posts/2022-07-23-my-keyboards/keymaps/bloid40.png" alt="" caption="QMK, Bluetooth" %}

Keycaps are TODO. 

My QMK-powered firmware is [here](https://github.com/hanhanhan-kim/qmk_firmware/tree/master/keyboards/handwired/bloid40). TODO UPDATE THIS LINK

&mu;c: ATMmega 32U4 on an [Adafruit Feather 32U4 Bluefruit](https://www.digikey.com/en/products/detail/adafruit-industries-llc/2829/5774320) breakout board. Uses BLE 2.4 GHz with a nRF51822 transceiver. 

Keymap updated 2023/10/15.

### Plaid (USB-C variant)
TODO

{% include figure image_path="/assets/images/posts/2022-07-23-my-keyboards/keymaps/plaidc_and_technik.png" alt="" caption="QMK, wired (same as Technik)" %}

Keycaps are TODO. 

My QMK-powered firmware is [here](https://github.com/hanhanhan-kim/qmk_firmware/tree/master/keyboards/dm9records/plaid/keymaps/hanhanhan-kim). TODO UPDATE THIS LINK

&mu;c: ATmega328P integrated into the main PCB. 

Keymap updated 2023/10/19.

### Technik 
TODO

{% include figure image_path="/assets/images/posts/2022-07-23-my-keyboards/keymaps/plaidc_and_technik.png" alt="" caption="QMK, wired, + RGB matrix" %}

Keycaps are TODO. 

My QMK-powered firmware is [here](https://github.com/hanhanhan-kim/qmk_firmware/tree/master/keyboards/boardsource/technik_o/keymaps/hanhanhan-kim). TODO UPDATE THIS LINK

&mu;c: TODO (STM something) integrated into the main PCB. 

Keymap updated 2023/10/19.

### Atlas
TODO

{% include figure image_path="/assets/images/posts/2022-07-23-my-keyboards/keymaps/atlas.png" alt="" caption="QMK, wired, + RGB, + extra row" %}

My QMK-powered firmware is [here](https://github.com/hanhanhan-kim/qmk_firmware/blob/master/keyboards/cannonkeys/atlas/keymaps/hanhanhan-kim/keymap.c). TODO UPDATE THIS LINK

&mu;c: STM32F072C0T6 integrated into the main PCB. As of 2023/10/21, this particular STM32 chip requires using a USB hub when flashing the keyboard (thanks QMK Discord for solving this one). Hardware is strange. 

### Brane

#TODO: pic

My QMK-powered firmware is [here](TODO: the brick QMK firmware) '

&mu;c: ATMega32U4 integrated into the main PCB. 

Keymap updated 2023/10/19.

<!-- ### Gridiron

### Plasticity

### Oddball

### Boardwalk -->



## Split Keyboards

### Torn
TODO

TODO: pic

Keycaps are TODO. 



My QMK-powered firmware is [here](https://github.com/hanhanhan-kim/qmk_firmware/tree/master/keyboards/torn/keymaps/hanhanhan-kim). TODO UPDATE THIS LINK

### Corne
My first split keyboard, and my first [ZMK](zmk.dev) build! I chose ZMK as my firmware framework because I wanted to build a 'true' split wireless build, where both halves are wireless, but would be read as a single device, as opposed to two separate devices (which is weird, because each keyboard half actually has its own µC). 

{% include figure image_path="/assets/images/posts/2022-07-23-my-keyboards/keymaps/corne.png" alt="" caption="ZMK, true wireless" %}

My ZMK-powered firmware is [here](https://github.com/hanhanhan-kim/zmk-config/blob/master/config/corne.keymap). TODO UPDATE THIS LINK

### Oddball

<!-- ### Let's Split
TODO -->
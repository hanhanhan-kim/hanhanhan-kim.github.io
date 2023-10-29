---
tags: 
    - HIDs
    - Tracking
excerpt: ":keyboard: A running record of my many keyboards."
header:
    og_image: /assets/images/posts/2023-10-28-my-keyboards/kbd_photos/brane.jpg
    teaser: /assets/images/posts/2023-10-28-my-keyboards/kbd_photos/brane.jpg
    header: /assets/images/posts/2023-10-28-my-keyboards/kbd_photos/brane.jpg
    overlay_image: /assets/images/posts/2023-10-28-my-keyboards/kbd_photos/brane.jpg
---
I've built a lot of 'weird' keyboards using [QMK](https://qmk.fm/) or [ZMK](https://zmk.dev/) to write the firmwares. Check out my keebs:

## Void 40

{% include figure image_path="/assets/images/posts/2023-10-28-my-keyboards/kbd_photos/void40.jpg" alt="" caption="Keycaps are [YMDK laser-etched keycaps](https://www.amazon.com/gp/product/B07JKTQJQ7/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&th=1), switches are [Cherry MX blacks](https://www.cherrymx.de/en/cherry-mx/mx-original/mx-black.html) (linear, 60 g actuation force, 85 g bottoming-out force), plate is 3D-printed integrated into the case, mounting style is integrated mount, mods are none." %}

<!-- {% include figure image_path="/assets/images/posts/2022-07-23-my-keyboards/keymaps/void40.png" alt="" caption="QMK, wired, + rotary encoder. Keymap last updated on 2023/10/15." %} -->

**QMK-powered firmware:** [here](https://github.com/hanhanhan-kim/qmk_firmware/tree/hank/keyboards/void40). 

**&mu;c:** ATMmega 32U4 on a [Sparkfun Qwiic Pro Micro USB-C](https://www.digikey.com/en/products/detail/sparkfun-electronics/DEV-15795/11594572) breakout board.

My first mechanical keyboard, as well as my first 40%  and ortholinear keyboard. I thought the [Void 40](https://victorlucachi.ro/projects/void40/) would be a fun weekend project and talking piece, and that I'd never actually use the board. Once I finished building it, however, I started typing on it. Much to my surprise, I found the compact board to be incredibly comfortable. No more stretching my fingers out to reach numbers and symbols, and I never had to move my wrists, except when reaching for the mouse. I also learned that I hit the "b" key with my right hand, because on a traditional staggered keyboard, the "b" is smack dab in the middle, and I'm right-hand dominant. Apparently, a refined individual is supposed to hit the "b" with the left hand though, and the ortholinearity of the Void 40 emphasized that notion. So, arguably, using an ortholinear board encouraged me to adopt better typing habits.

## Planck in Custom 'Planckeneko' Case

{% include figure image_path="/assets/images/posts/2023-10-28-my-keyboards/kbd_photos/planckeneko.jpg" alt="" caption="Keycaps are [Drop MT3 white-on-black](https://drop.com/buy/drop-mt3-white-on-black-keycap-set?defaultSelectionIds=965854), switches are [Gateron Oil Kings](https://divinikey.com/products/gateron-oil-king-linear-switches) (linear, 55 g actuation force, 65 g bottoming-out force), plate is brass, mounting style is o-ring gasket mount, mod is painter's tape on PCB." %}

**QMK-powered firmware:** [here](https://github.com/hanhanhan-kim/qmk_firmware/tree/hank/keyboards/planck/keymaps/hanhanhan-kim).

**&mu;c:** ARM STM32 integrated into the main PCB. 

I used the PCB from the popular Planck, but I use the "[Unified Daughterboard Project](https://github.com/Unified-Daughterboard/)" to separate out the USB-C port from the rest of the PCB. Doing so enabled me to gasket-mount the 'motherboard' PCB, such that during typing use, the motherboard can 'bounce' on the gasket, without also bouncing the USB port (motherboard + daughterboard format breaks the rigid relationship between the USB port and the rest of the keyboard). I designed the case from scratch, and had it machined at [JLCPCB](https://3d.jlcpcb.com/cnc-machining). I provide open-sourced files for the case design [here](https://github.com/hanhanhan-kim/kbd-cases/tree/main/planckeneko). 

<!-- {% include figure image_path="/assets/images/posts/2022-07-23-my-keyboards/keymaps/planck.png" alt="" caption="QMK, wired, + rotary encoder, + RGB, + music (e.g. MIDI)" %} -->

## Bloid 40

{% include figure image_path="/assets/images/posts/2023-10-28-my-keyboards/kbd_photos/bloid40.jpg" alt="" caption="Keycaps are [YMDK laser-etched keycaps](https://www.amazon.com/gp/product/B07TLX2N6K/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&th=1), switches are [Cherry MX blacks](https://www.cherrymx.de/en/cherry-mx/mx-original/mx-black.html) (linear, 60 g actuation force, 85 g bottoming-out force), plate is 3D-printed integrated into the case, mounting style is integrated mount, mods are none." %}

**QMK-powered firmware:** [here](https://github.com/hanhanhan-kim/qmk_firmware/tree/master/keyboards/handwired/bloid40). 

**&mu;c:** ATMmega 32U4 on an [Adafruit Feather 32U4 Bluefruit](https://www.digikey.com/en/products/detail/adafruit-industries-llc/2829/5774320) breakout board. Uses BLE 2.4 GHz with a nRF51822 transceiver. 

This keyboard is basically the  [Void 40](https://victorlucachi.ro/projects/void40/), but with some changes I made to accommodate for Bluetooth. I designed and built this keyboard for use with QMK, before [ZMK](https://zmk.dev/) became a thing. If you're looking to build a wireless custom keyboard, I'd _highly_ recommend using ZMK and using a ZMK-compatible &mu;c. ZMK should be used for any wireless keyboard build. For wired builds, I think QMK is still better. I document my build of the Bloid40 [here](https://github.com/hanhanhan-kim/bloid40).

<!-- {% include figure image_path="/assets/images/posts/2022-07-23-my-keyboards/keymaps/bloid40.png" alt="" caption="QMK, Bluetooth, last updated 2023/10/15" %} -->

## Plaid (USB-C variant) in Custom 'Qlavier' Case

{% include figure image_path="/assets/images/posts/2023-10-28-my-keyboards/kbd_photos/plaid.jpg" alt="" caption="Keycaps are [NP PBT blank keycaps](https://divinikey.com/products/np-pbt-blank-white-keycap-set), switches are [Gateron KS-3 Milky Yellow Pro Linear Switches](https://divinikey.com/products/gateron-ks-3-milky-yellow-pro-linear-switches) (linear, 50 g actuation force, 62 g bottoming-out force), plate is FR4, mounting style is gummy-ring mount, mods are none." %}

**My QMK-powered firmware:** [here](https://github.com/hanhanhan-kim/qmk_firmware/tree/hank/keyboards/dm9records/plaid).

**&mu;c:** ATmega328P integrated into the main PCB. 

This keyboard is the [USB-C fork of the popular Plaid keyboard](https://github.com/piit79/plaid-c). I designed the stacked laser-cut case from scratch, and had a friend laser-cut the files. I provide open-sourced files for the case design [here](https://github.com/hanhanhan-kim/kbd-cases/tree/main/qlavier-style-plaid). 

<!-- {% include figure image_path="/assets/images/posts/2022-07-23-my-keyboards/keymaps/plaidc_and_technik.png" alt="" caption="QMK, wired (same as Technik), last updated 2023/10/19" %} -->

## Atlas

{% include figure image_path="/assets/images/posts/2023-10-28-my-keyboards/kbd_photos/atlas.jpg" alt="" caption="Keycaps are [ePBT x GOK Kuro/Shiro keycaps](https://kbdfans.com/products/kuro-shiro-r3), switches are [Gazzew Boba U4Ts](https://swagkeys.com/products/gazzew-u4t-boba-switches?variant=43620145168637) (tactile, 62 g actuation force),, plate is brass, mounting style is top mounted, mods are [StupidFish EVA plate foam set designed for Preonic](https://stupidfish.design/products/preonic-v3-case-and-plate-foam-set) and painter's tape on PCB." %}

**My QMK-powered firmware:** [here](https://github.com/hanhanhan-kim/qmk_firmware/tree/hank/keyboards/cannonkeys/atlas/keymaps/hanhanhan-kim).

**&mu;c:** STM32F072C0T6 integrated into the main PCB. As of 2023/10/21, this particular STM32 chip requires using a USB hub when flashing the keyboard (thanks QMK Discord for solving this one). Hardware is strange. 

This keyboard is the [Cannon Keys Atlas ortholinear keyboard](https://cannonkeys.com/products/atlas-keyboard). I use this keyboard for playing computer games, because I need access to number keys, modifier keys, and alpha keys, on the same layer, when playing games. This keyboard supports some fun RGB backlighting effects. I document my build of this keyboard [here](/_posts/2022-07-22-modding-the-atlas-keyboard.md). Fun fact, the current keycaps are mostly the [ePBT x GOK Kuro/Shiro keycaps](https://kbdfans.com/products/kuro-shiro-r3), mixed in with the spacebar and the "super" key of the [Drop black-on-white DCX keycap set](https://drop.com/buy/drop-dcx-black-on-white-keycap-set). The combination looks pretty seamless to me.

I use this keyboard a lot. Recently, I've had to solder some of the switches directly into the PCB, because the Kailh hot-swap sockets have started to tear off the circuit board. I heard this could be an issue with frequent hot swapping, but I never actually experienced the issue until now. Basically, every time one inserts a switch into a socket, a little bit of friction from the insertion pushes the hot-swap socket back and away from the PCB. The hot-swap sockets are soldered onto pads, not throughholes, of the PCB, so the sockets aren't affixed to the PCB in a reliable way. On a similar note, I've had to jump some connections on the keyboard matrix, because the PCB joints near the sockets have started to fray. 

<!-- {% include figure image_path="/assets/images/posts/2022-07-23-my-keyboards/keymaps/atlas.png" alt="" caption="QMK, wired, + RGB, + extra row" %} -->

## Brane

{% include figure image_path="/assets/images/posts/2023-10-28-my-keyboards/kbd_photos/brane.jpg" alt="" caption="Keycaps are [GMK Botanical 2 keycaps](https://omnitype.com/products/gmk-botanical-2-keycap-set), switches are [C3 Equalz TKC Dark Green Tangerine V2s](https://divinikey.com/products/gateron-ks-3-milky-yellow-pro-linear-switches) (linear, 67 g actuation force), plate is POM, mounting style is gasket mount, mod is EVA plate foam." %}

**My QMK-powered firmware:** [here](https://github.com/hanhanhan-kim/qmk_firmware/tree/hank/keyboards/brane).

**&mu;c:** ATMega 32U4 integrated into the main PCB. 

This keyboard comes from [P3D Store](https://p3dstore.com/), which sadly no longer operates. The case is cerakoted, and the back features an artsy engraving of a brain. This keyboard supports RGB backlighting effects, but I never use them. They don't work with the aesthetic of this board, in my opinion. This keyboard is arguably my most premium board. It looks and sounds incredible. 

<!-- Keymap updated 2023/10/19. -->

## Technik 

{% include figure image_path="/assets/images/posts/2023-10-28-my-keyboards/kbd_photos/technik.jpg" alt="" caption="Keycaps are [wrk.Legend keycaps](https://worklouder.cc/shop/wrk-legend/), switches are [Kailh Low Profile v1 Choc Silvers](https://mkultra.click/choc-switches) (linear, 40 g actuation force), plate is FR4, mounting style is tray mount, mods are none." %}

**My QMK-powered firmware:** [here](https://github.com/hanhanhan-kim/qmk_firmware/tree/master/keyboards/boardsource/technik_o/keymaps/hanhanhan-kim). 

**&mu;c:** Some kind of STM32 integrated into the main PCB. 

This keyboard comes from [Boardsource](https://www.boardsource.xyz/products/Technik). I'm using a black aluminium case. 

<!-- {% include figure image_path="/assets/images/posts/2022-07-23-my-keyboards/keymaps/plaidc_and_technik.png" alt="" caption="QMK, wired, + RGB matrix, keymap last updated 2023/10/19" %} -->

## Techinkable

{% include figure image_path="/assets/images/posts/2023-10-28-my-keyboards/kbd_photos/technikable.jpg" alt="" caption="Keycaps are [MBK Lgends WoB Hiragana alphas and mods](https://www.boardsource.xyz/products/MBK_Legend), switches are [Kailh Low Profile v1 Choc Silvers](https://mkultra.click/choc-switches) (linear, 40 g actuation force), plate is FR4, mounting style is tray mount, mods are none." %}

**My ZMK-powered firmware:** [here](https://github.com/hanhanhan-kim/zmk-config)

**&mu;c:** I'm actually not sure, I never took a look at the label on the chip. The &mu;c is integrated into the PCB. 

This keyboard comes from [Boardsource](https://old.boardsource.xyz/store/620fdd96ada5400fd302727d) and is designed by Pete Johanson of ZMK, himself. This keyboard is a seamless Bluetooth keyboard. 

## Faux-Fox Keyboard V2

{% include figure image_path="/assets/images/posts/2023-10-28-my-keyboards/kbd_photos/ffkb_v2.jpg" alt="" caption="Keycaps are [MBK Lgends BoW alphas and mods](https://www.boardsource.xyz/products/MBK_Legend), switches are [Kailh Low Profile v1 Choc Silvers](https://mkultra.click/choc-switches) (linear, 40 g actuation force), plate is none, mounting style is tray mount, mods are none." %}

**My ZMK-powered firmware:** :construction:

**&mu;c:** Nordic nRF52840 on a nice!nano v2 breakout board.

The PCB for [this keyboard](https://fingerpunch.xyz/product/faux-fox-keyboard/) is designed by [Sadek Baroudi](https://github.com/sadekbaroudi) of [Fingerpunch](https://fingerpunch.xyz/). I got the case for this keyboard resin-printed at [JLCPCB](https://3d.jlcpcb.com/). I spray-painted the case in blue. I installed a [Cirque trackpad](https://www.cirque.com/glidepoint-circle-trackpads) onto this keyboard, even though ZMK doesn't yet support Cirque hardware.... A bit of an oversight on my part. I'm married to the idea though, so I'm waiting for ZMK to start supporting the Cirque trackpads one day. There is at least one fork out there that experimentally supports the Cirque, but I haven't gotten around to tinkering with those forks yet. I'm using a pair of cool EVQWGD001 horizontal rotary encoders. I document my build of the keyboard [here](/_posts/2022-09-28-building-the-ffkb-keyboard.md).

## Libra Mini

{% include figure image_path="/assets/images/posts/2023-10-28-my-keyboards/kbd_photos/libra_mini.jpg" alt="" caption="Keycaps are clones of [ePBT cool kids](https://candykeys.com/group-buys/epbt-cool-kids), switches are [Gazzew Boba U4Ts](https://swagkeys.com/products/gazzew-u4t-boba-switches?variant=43620145168637) (tactile, 62 g actuation force), plate is acrylic, mounting style is gasket mount, mods are painter's tape on PCB and case weighting with car muffler." %}

**My QMK-powered firmware:** :construction:

&mu;c: ATMega 32U4 on an Arduino Nano clone breakout board.

I got this keyboard from AliExpress. The joystick is pretty cool. Given that this keyboard is a staggered layout, I don't ever actually use it. It's more of a decorative piece. I found the firmware for this keyboard as [VIA](https://www.caniusevia.com/)-compatible `.json` file. I plan on rewriting the firmware for QMK. 

<!-- ## Gridiron

## Plasticity

## Oddball

## Boardwalk -->

## Corne (full wireless)

{% include figure image_path="/assets/images/posts/2023-10-28-my-keyboards/kbd_photos/corne_wireless_no_screens.jpg" alt="" caption="Keycaps are [MBK choc keycaps](https://mkultra.click/mbk-choc-keycaps/), switches are [Kailh Low Profile v1 Choc Browns](https://mkultra.click/choc-switches) (tactile, 60 g actuation force), plate is FR4, mounting style is tray mount, mods are none" %}

**My ZMK-powered firmware:** [here](https://github.com/hanhanhan-kim/zmk-config).

**&mu;c:** Two Nordic nRF52840s on nice!nano v2 breakout boards (one per keyboard half). 

My first true wireless split keyboard, where both halves are wireless. This keyboard is still read as a single device (as it should), as opposed to two separate devices, even though each keyboard half actually has its own &mu;c. 

<!-- {% include figure image_path="/assets/images/posts/2022-07-23-my-keyboards/keymaps/corne.png" alt="" caption="ZMK, true wireless" %} -->

## Corne (wired with OLEDs)

{% include figure image_path="/assets/images/posts/2023-10-28-my-keyboards/kbd_photos/corne_wired.jpg" alt="" caption="Keycaps are [MBK choc keycaps](https://mkultra.click/mbk-choc-keycaps/), switches are [Kailh Low Profile v1 Choc Jades](https://chosfox.com/products/kailh-low-profile-choc-switches?variant=42514647843010) (clicky, 50 g actuation force), plate is none, mounting style is none, mods are none." %}

**My QMK-powered firmware:** [here](https://github.com/hanhanhan-kim/qmk_firmware/tree/hank/keyboards/crkbd/keymaps/hanhanhan-kim).

**&mu;c:** Two ATMega 32U4s Bit-C breakout boards (one per keyboard half). 

This keyboard features two OLED screens. The left half of the keyboard featuers an animation with a WPM display. The animation animates faster as the user types faster. I document my build of this keyboard [here](/_posts/2022-09-18-building-a-torn-kbd.md). 

<!-- ### Torn

### Oddball -->
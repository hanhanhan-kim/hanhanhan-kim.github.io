---
title: Uploading Keyboard Bootloaders
tags:
    - HIDs
    - Tracking
excerpt: ":boot: My struggle with uploading bootloaders onto keyboards."
header:
    header: /assets/images/posts/2022-08-10-kbd-bootloaders/cover.jpg
    teaser: /assets/images/posts/2022-08-10-kbd-bootloaders/cover.jpg
    og_image: /assets/images/posts/2022-08-10-kbd-bootloaders/cover.jpg
    overlay_image: /assets/images/posts/2022-08-10-kbd-bootloaders/cover.jpg
---

For whatever reason, uploading bootloaders to virgin µC ICs really trips me up. This post is a running document of bootloader uploading protocols, for keyboards I've built that do not use a dev board (e.g. the Arduino Pro Micro, the Nice!Nano, etc.). I'll say it now . . . 99% of the time, my struggles have to do with me cloning the wrong GitHub branch . . . . I use a Linux (Ubuntu) system for this kind of thing. This blog post assumes that **_you already know how to use [QMK](https://qmk.fm/)_**. 

## Plaid
FYI, I'm using the [fork of the Plaid with a USB-C port](https://github.com/piit79/plaid-c). The following instructions also work for the [original Plaid with a USB mini B port](https://github.com/hsgw/plaid).

Purchase a USBasp programmer with an ICSP pin adaptor (ASIN [B0885RKVMC](https://www.amazon.com/KeeYees-Downloader-Programmer-Adapter-Microcontroller/dp/B0885RKVMC/ref=sr_1_4?crid=3RBGKUJSWRSK&keywords=usbasp+bootloader&qid=1660188847&sprefix=usbasp+bootloader%2Caps%2C111&sr=8-4)). 

Git clone the `plaid` branch of `hsgw`'s `USBaspLoader` fork:

```bash
git clone -b plaid https://github.com/hsgw/USBaspLoader.git
```

Rename the directory from `UsbaspLoader` to `USBaspLoader-plaid`, just so you don't get confused if you have to upload the bootloader for other keyboards via USBasp. Then, `cd` into the root of the `USBaspLoader-plaid` directory. Open up the `Makefile.inc` file with your favourite text editor. Observe lines 39-41 of the `Makefile.inc`:

```make
# PROGRAMMER contains AVRDUDE options to address your programmer
# PROGRAMMER = -c pony-stk200
# PROGRAMMER = -c usbasp
PROGRAMMER = -c avrispmkII -P usb -v
```

Change the `PROGRAMMER` to `-c usbasp`, because we're using a USBasp bootloader:

```make
# PROGRAMMER contains AVRDUDE options to address your programmer
# PROGRAMMER = -c pony-stk200
PROGRAMMER = -c usbasp
# PROGRAMMER = -c avrispmkII -P usb -v
```

Connect the ICSP cable from the USBasp programmer device, to the 6-pin ICSP header on the Plaid PCB. 

{% include figure image_path="/assets/images/posts/2022-08-10-kbd-bootloaders/plaid-connection.jpg" alt="" caption="Note the orientation of the ICSP cable. The labelled MISO pin on the USBasp programmer's cable should line up with the triangle vertex on the Plaid PCB's ICSP pinout. The triangle vertex on the PCB should look like the triangle I drew on this image." %}

Do not yet plug in the USB cable. Only the ICSP cable should be plugged in. From `USBaspLoader-plaid`, which has the `makefile.inc` file, run the following:

```bash
make flash
```

The result of the above command should look something like the terminal output below:

{% include figure image_path="/assets/images/posts/2022-08-10-kbd-bootloaders/plaid-make-flash.png" alt="" caption="The left side of the screenshot shows the modified <code>makefile.inc</code>, and the right side shows the output of the <code>make flash</code> command." %}

Unplug the ICSP header, and plug in the USB cable. Then, follow the instructions from the [official Plaid docs](https://github.com/hsgw/plaid/blob/master/doc/en/bootloader.md). That is:

1. Push and hold the RESET switch.
2. Push and hold the BOOST switch.
3. Release the RESET switch.
4. Release the BOOT switch. 

Then, navigate to your `qmk_firmware` directory, and flash the Plaid's firmware like you would for any QMK-compatible keyboard:

```bash
qmk flash -kb dm9records/plaid
```

The result of the above command should look something like terminal output below:

![](/assets/images/posts/2022-08-10-kbd-bootloaders/plaid-flash.png)

You might be a little confused though, because the Plaid keyboard's power LED won't be lit. No worries though, just power cycle the keyboard---unplug and replug the USB cable. The keyboard's power LED should now be lit. At this point, the bootloader is correctly loaded onto the keyboard, and we can upload QMK firmware via USB :tada:. Just run `qmk flash -kb dm9records/plaid`, and then either hit the BOOT switch, or if you have a key mapped to [`QK_BOOT`](https://docs.qmk.fm/#/quantum_keycodes?id=qmk-keycodes), press that key. In other words, flash the keyboard like normal :smile:. 

<!-- ## Torn -->
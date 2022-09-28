---
title: Building a Wireless FFKB (v2) Keyboard
excerpt: ":fox_face: Yet another keyboard build! This one has a trackpad!"
tags:
    - HIDs
    - Builds
header:
    og_image: /assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/18.jpg
    teaser: /assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/18.jpg
    header: /assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/18.jpg
    overlay_image: /assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/18.jpg
---

Not too long ago, I purchased a [Libra Mini](https://www.google.com/search?q=libra+mini&rlz=1C1VDKB_enUS957US957&sxsrf=ALiCzsY5J9nfN3gYJFisTerYzEDsZyq7gA:1660106376757&source=lnms&tbm=isch&sa=X&ved=2ahUKEwi4yYCXurv5AhUUIkQIHbpBClQQ_AUoAXoECAIQAw&biw=2560&bih=1272&dpr=1) from AliExpress, and I absolutely love it. The only problem is that it's row-staggered like a traditional keyboard ... but I liked the [Alice](https://geekhack.org/index.php?topic=95054.0)-esque monoblock style, as well as the tenting. so I went about looking for a column-staggered board with those features. I couldn't find a tented column-staggered keyboard[^1], but I did find some promising 'split' monoblock style boards, like the [babyV](https://eyeohdesigns.com/products/babyv) by [Eye Oh Designs](https://eyeohdesigns.com/), and the [Faux Fox](https://fingerpunch.xyz/product/faux-fox-keyboard-v2/) or FFKB by [Fingerpunch](https://fingerpunch.xyz/). I thought both these boards looked really nice, but I was really smitten by the FFKB. It can support a [Cirque trackpad](https://www.cirque.com/glidepoint-circle-trackpads) in the middle, as well as both EC11-style and [EVQWGD001](https://www.aliexpress.com/i/2251832804635444.html?gatewayAdapt=4itemAdapt)-style rotary encoders. I can also use a [Nice!Nano (v2)](https://nicekeyboards.com/docs/nice-nano/) as the µC and [ZMK](https://zmk.dev/) firmware, to make the keyboard wireless. In this post, I document my build of the FFKB (V2). 

## Case

One of the awesome things about the FFKB keyboard is its incredible modularity. You can add all sorts of different kinds of rotary encoders, or an OLED screen, or a trackpad, or hardware functions for a wireless build (e.g. a hardware power switch), or low pro or regular mechanical swtiches. To accommodate for all this modularity, [a few case options are available](https://github.com/sadekbaroudi/fingerpunch/tree/master/keyboards/ffkb) on Sadek's GitHub. I'm building with hot swap choc low pro switches, EVQ11 rotary encoders, a Cirque trackpad, and wireless functionality. The corresponding case for these hardware features is [this top case](https://github.com/sadekbaroudi/fingerpunch/blob/master/keyboards/ffkb/cases/stls/v2/low-pro/ff-ul-6-c-ev-mx-w.stl) and [this bottom case](https://github.com/sadekbaroudi/fingerpunch/blob/master/keyboards/ffkb/cases/stls/v2/low-pro/ff-ul-6-bot-w.stl). The top case has "mx" in its title, but in this case, the "mx" just denotes that the case is tall enough to accommodate for regular LiPoly battery thicknesses. 

I got my case parts printed in white nylon from [PCBWay](https://www.pcbway.com/). I then tried my hand at spray painting the case parts! I used some twine to hang the parts in midair, and I placed a cardboard box underneath, so no off-target paint would reach the patio floor. I'm using a [Rust-Oleum Satin Wildflower Blue](https://www.rustoleum.com/product-catalog/consumer-brands/painters-touch-2x-ultra-cover/satin?ls=249062&lc=Satin%20Wildflower%20Blue) spray can that I picked up from Home Depot. This paint colour sprays very smoothly and evenly, and is very easy to use. 

![](/assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/spray-paint.jpg)

After 4 layers, I managed to cover all the case parts. I think the end result looks pretty good!

![](/assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/sprayed.jpg)

## Electronics

1. **Solder the hot-swap sockets**. I plan on supporting hot swap low pro Choc switches, so I solder low pro Choc sockets to the bottom of the PCB. The bottom of the PCB features a reset button. 

    {% include figure image_path="/assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/0.jpg" caption="A reset button denotes the bottom side of the PCB, which I've marked with a red arrow."%}

2. **Solder the µC to the PCB**. The bottom of the PCB features a reset button. We want to solder the µC to the top side of the PCB. If you plan on socketing the µC, make sure you use one of the [thin Mill-Max sockets](https://www.digikey.com/en/products/detail/mill-max-manufacturing-corp/115-93-624-41-003000/81896), or else the µC's USB port will not fit in the case. 

    {% include figure image_path="/assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/1.jpg" caption="Solder the µC, or if applicable, the socket, to the top side of the PCB."%}

    I'm using a Nice!Nano as my µC, so I need to solder an extra set of 1 x 3 headers to the PCB, as specified in the [official docs](https://github.com/sadekbaroudi/fingerpunch/tree/master/ffkb). 

    <figure class="third">
    <a href="/assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/2.jpg"><img src="/assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/2.jpg"></a>
    <a href="/assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/3.jpg"><img src="/assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/3.jpg"></a>
    <a href="/assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/4.jpg"><img src="/assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/4.jpg"></a>
    <figcaption>For the Nice!Nano, solder another 1 x 3 header pins onto the µC. Clip off the excess header pins. Note that even though I socketed the µC, the socket I used doesn't support the extra 1 x 3 pins I soldered here. So, removing the µC from the main PCB would require me to desolder the 1 x 3 pins, but I wouldn't need to desolder anything else.</figcaption>
    </figure>

3. **Solder the rotary encoders**. I've always wanted to use EVQWGD001-style rotary encoders, and now's my chance! I solder the rotary encoders to the top of the PCB. In the future, I'll probably try and design my own keyboard, or handwire something, that supports these cool and very ergonomic encoders. 

    ![](/assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/5.jpg)

4. **Connect the Cirque trackpad**. Here's the really fun part! The FFKB (v2) is pretty cool in that the Cirque trackpad spot can be replaced with a different feature, such as an OLED screen, or an EC11 rotary encoder. I've opted for the Cirque trackpad, because I've seen many keyboards support OLEDs and rotary encoders, but I've rarely seen one that supports a trackpad. 

    We first have to make sure that the R1 resistor is removed from the back of the trackpad, so the trackpad's I2C protocol is enabled. In my case, the R1 resistor was already removed! Presumably, [Sadek](https://github.com/sadekbaroudi), the founder of [Fingerpunch](https://fingerpunch.xyz/), already did this step for me :tada:. 

    {% include figure image_path="/assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/6.jpg" caption="Remove the R1 resistor, indicated with the blue arrow, to enable the I2C protocol. Mine was already removed!"%}

    Then, insert the trackpad into the case, such that the divots on the trackpad align with the protrusions on the case. 

    {% include figure image_path="/assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/7.jpg" caption="Align the trackpad to the case, via the markings indicated with the red arrows."%}

    After lining up the trackpad to the case, I use some hot glue to secure everything in place. I also connect the flat cable to the trackpad, such that the metal side of the cable contacts the metal parts of the trackpad socket. 
    
    ![](/assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/8.jpg)

    We're then going to thread the other end of the cable via the PCB's 'slot' hole, from the top side of the PCB to the bottom side. The cable should then plug into the socket on the bottom of the PCB. 

    <figure class="half">
    <a href="/assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/9.jpg"><img src="/assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/9.jpg"></a>
    <a href="/assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/10.jpg"><img src="/assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/10.jpg"></a>
    <figcaption>The first image shows the trackpad cable connected to the PCB socket. The second image shows the trackpad cable connected to the trackpad.</figcaption>
    </figure>


    Let's just take a look at the trackpad with the top case, and admire our work so far!

    ![](/assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/11.jpg)

5. **Connect the battery switch and JST socket**. Connecting a battery switch and a JST socket is necessary, only if you're doing a wireless build. I am, so I connected them! The [Fingerpunch Discord server](https://discord.gg/ewS6xbCgPb) has a lot of great recommendations for doing alternative builds, and Sadek suggested a [2-pin JST connector](https://www.digikey.com/en/products/detail/jst-sales-america-inc/S2B-PH-K-S-LF-SN/926626?s=N4IgTCBcDaIDoBcAEAWArGgtARgOzYE5MA5AERAF0BfIA) and [this toggle switch](https://www.digikey.com/en/products/detail/c-k/OS102011MA1QN1/1981430) from Digikey, if building a wireless FFKB. The JST connector allows us to connect a LiPo battery in a reversible way, and the toggle switch lets us cut the battery's connection to the keyboard, so we conserve on battery life. The JST connector is a 2-pin, even though the keyboard PCB has 3 pins for the battery's JST---the reasoning is that if a battery already has a JST header crimped on, the VCC and GND cables may be fixed in one orientation or another, and may require the user to flip the battery's polarity, which can be annoying. 

    {% include figure image_path="/assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/12.jpg" caption="The battery power switch and the battery JST connector on the PCB. Note tha the PCB's silkscreen says 'red wire in the middle'. It refers to the VCC wire of the LiPo battery."%}

6. **Connect the battery**. I found a really cool [400 mAH battery on AliExpress](https://www.aliexpress.com/item/2251832549461803.html?spm=a2g0o.order_list.0.0.71be1802jGjzVA) that's only 3 mm in thickness. I extended the battery wires and crimped JST connectors onto the battery leads. 

    <figure class="half">
    <a href="/assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/13.jpg"><img src="/assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/13.jpg"></a>
    <a href="/assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/14.jpg"><img src="/assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/14.jpg"></a>
    <figcaption>Look at how thin the battery is! It sits even lower than the edges of the top case! I secured the battery to the PCB with some Kapton tape, like a professional.</figcaption>
    </figure>

    I'm really pleased with the dimensions of the battery. The battery's length and width are small enough that it doesn't interfere with the hot swap sockets, and it's also super thin. 

7. **Add the switches**. It's time to add the switches! I'm using [Brown Kailh Low Pro Choc](https://mkultra.click/choc-switches) switches (60 g, tactile).  The official docs say that it's better to add the switches on the outside columns, first, but I found that it didn't matter too much. Maybe Sadek revised the board for the later batches. 

    ![](/assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/15.jpg)

## Case and Keycaps

At this point, we're finished all the electronics. We just need to finish assembling the case together. We add 8 (or optionally, 9) M2 x 8 mm F-F hex standoffs to the allocated holes in the PCB. These holes should align with holes that are present on both the top and bottom case parts. 

{% include figure image_path="/assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/16.jpg" caption="The red arrows indicate the spots where I've dropped in the M2 F-F hex standoffs."%}

Then, we line up the bottom case part, and secure everything into the bottom case with M2 screws (the length doesn't really matter, so long as they're just long enough to reach the threads of the standoffs. In general, try to use the shortest screws you can get away with). We also apply some bumper stickers. 

![](/assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/17.jpg)

Finally, we flip the keyboard over, and screw in M2 screws into the hex standoffs from the top side, so that the top case is properly secured. We also pop in the keycaps. I'm using some [white MBK Legends](https://mkultra.click/mbk-legend-keycaps/). 

![](/assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/18.jpg)

Awesome! The hardware is all done :smile:!

## Firmware 

Next, we're going to upload some firmware! Admittedly, I should have thought about the firmware more ahead of time. I'm using a [Nice!Nano (v2) µC](https://nicekeyboards.com/nice-nano/), which at least for now (as of 2022/09/27) _requires_ that I use [ZMK](https://zmk.dev/) as the code base for generating the firmware. In some sense that's great, because ZMK's support for wireless keyboard builds is unmatched. The drawback, however, is that ZMK does not yet support pointing devices like the Cirque trackpad, which I have installed on my FFKB! So, my wireless trackpad FFKB build has incredible wireless support, but its trackpad is currently just an art piece :sweat_smile:. An alternate and OG codebase for generating keyboard firmware, [QMK](https://qmk.fm/), definitely supports pointing devices, like the Cirque trackpad, but it doesn't support the Nice!Nano µC .... Apparently, some talented people are working on implementing pointing devices (and specifically, the Cirque) into ZMK, so it sounds like I can just wait, and eventually all my desired functions will be integrated into ZMK and by extension, my FFKB. 

Something worth noting for folks is that Sadek likes to keep his GitHub code separate from main repos, like the main [QMK](https://github.com/qmk/qmk_firmware) and [ZMK](https://github.com/zmkfirmware/zmk) repos. Fortunately, using Sadek's ZMK code is very straightforward! We first fork [Sadek's `zmk-ffkb` repo](https://github.com/sadekbaroudi/zmk-ffkb). Then, we make changes to the local [keymap file](https://github.com/sadekbaroudi/zmk-ffkb/blob/master/config/boards/shields/ffkb/ffkb.keymap), as desired. Then, we go to the webpage where our fork is, and make sure that GitHub Actions is enabled (I think you just need to click a green "accept" button on the webpage). At this point, everything's the same as a [regular ZMK configuration](https://zmk.dev/docs/user-setup). We add, commit, and push our changes, then navigate to the GitHub Actions tab, and download the generated `firmware.zip` artifact. We extract the `firmware.zip`, put our keyboard into bootloader mode via double-clicking the reset button on the back of the keyboard (which tricks the computer into thinking the keyboard is a sort of mass storage device), and drag the `.UF2` file into the keyboard / Nice!Nano 'mass storage device'. If there are ever any questions, I can highly recommend the [Fingerpunch Discord server](https://discord.gg/ewS6xbCgPb). It's a _super_ helpful and responsive community! 

## Footnotes
[^1]: Spoiler, I did not find a non-row-staggered monoblock keyboard that is also tented. I guess it's kind of a niche build, because the sort of person who would desire a tented keyboard, is the sort of person who is hyper ergonomics-oriented ... and so they would insist on not only a tented keyboard, but also a true split keyboard. There are a lot of tented keyboards out there, but not too many tented monoblock keyboards. Maybe I'll design and make one. 
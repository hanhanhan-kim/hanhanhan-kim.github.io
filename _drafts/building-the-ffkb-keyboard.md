---
title: Building a Wireless FFKB (v2) Keyboard
excerpt: ":fox_face: Yet another keyboard build! This one has a trackpad!"
tags:
    - HIDs
    - Builds
header:
    og_image: /assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/16.jpg
    teaser: /assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/16.jpg
    header: /assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/16.jpg
    overlay_image: /assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/16.jpg
---

Not too long ago, I purchased a [Libra Mini](https://www.google.com/search?q=libra+mini&rlz=1C1VDKB_enUS957US957&sxsrf=ALiCzsY5J9nfN3gYJFisTerYzEDsZyq7gA:1660106376757&source=lnms&tbm=isch&sa=X&ved=2ahUKEwi4yYCXurv5AhUUIkQIHbpBClQQ_AUoAXoECAIQAw&biw=2560&bih=1272&dpr=1) from AliExpress, and I absolutely love it. The only problem is that it's row-staggered like a traditional keyboard ... but I liked the [Alice](https://geekhack.org/index.php?topic=95054.0)-esque monoblock style, as well as the tenting. so I went about looking for a column-staggered board with those features. I couldn't find a tented column-staggered keyboard[^1], but I did find some promising 'split' monoblock style boards, like the [babyV](https://eyeohdesigns.com/products/babyv) by [Eye Oh Designs](https://eyeohdesigns.com/), and the [Faux Fox](https://fingerpunch.xyz/product/faux-fox-keyboard-v2/) or FFKB by [Fingerpunch](https://fingerpunch.xyz/). I thought both these boards looked really nice, but I was really smitten by the FFKB. It can support a [Cirque trackpad](https://www.cirque.com/glidepoint-circle-trackpads) in the middle, as well as both EC11-style and [EVQWGD001](https://www.aliexpress.com/i/2251832804635444.html?gatewayAdapt=4itemAdapt)-style rotary encoders. I can also use a [Nice!Nano (v2)](https://nicekeyboards.com/docs/nice-nano/) as the µC and [ZMK](https://zmk.dev/) firmware, to make the keyboard wireless. In this post, I document my build of the FFKB (V2). 

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
    <figcaption>Look at how thin the battery is! It sits even lower than the edges of the top case!</figcaption>
    </figure>

    I'm really pleased with the dimensions of the battery. The battery's length and width are small enough that it doesn't interfere with the hot swap sockets. 

    ![](/assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/15.jpg)

7. **Add the switches**. It's time to add the switches! I'm using [Brown Kailh Low Pro Choc](https://mkultra.click/choc-switches) switches (60 g, tactile).  The official docs say that it's better to add the switches on the outside columns, first, but I found that it didn't matter too much. Maybe Sadek revised the board for the later batches. 

    ![](/assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/16.jpg)

## Case

## Finishing Touches

## Future Improvements

## Footnotes
[^1]: Spoiler, I did not find a non-row-staggered monoblock keyboard that is also tented. I guess it's kind of a niche build, because the sort of person who would desire a tented keyboard, is the sort of person who is hyper ergonomics-oriented ... and so they would insist on not only a tented keyboard, but also a true split keyboard. There are a lot of tented keyboards out there, but not too many tented monoblock keyboards. Maybe I'll design and make one. 
---
title: Building a Small Form Factor PC
tags:
    - Computers
    - Builds
excerpt: ":desktop_computer: Building a Small Form Factor PC (SFFPC) for personal use."
header:
    og_image: /assets/images/posts/2022-09-18-building-a-sffpc/49.jpg
    teaser: /assets/images/posts/2022-09-18-building-a-sffpc/49.jpg
    header: /assets/images/posts/2022-09-18-building-a-sffpc/49.jpg
    overlay_image: /assets/images/posts/2022-09-18-building-a-sffpc/49.jpg
---

I've wanted to build a small form factor PC (SFFPC) for quite some time. One of my favourite technology YouTube channels is [Optimum Tech](https://www.youtube.com/c/OptimumTech), and the host specializes in building small ITX form factor PC builds. At this point, building a SFFPC is not super niche, and there's a [sizeable community](https://www.reddit.com/r/sffpc/) surrounding it. 

## The Case
SFFPC builds revolve around the PC case, because that's what limits the size, and to some extent, the power[^1] of the build. SFFPC expert, Optimum Tech, has a really high opinion of the FormD T1.

{% include video id="RcLdVLr3Oy8" provider="youtube" %}

The FormD T1 comes in three possible layouts: the reference layout, the tower layout, and the sandwich layout. Optimum Tech argues that the sandwich layout provides the best cooling performance, and so I purchased a FormD T1-SW case in all black. It arrived flat-packed after a few weeks, and I used the [online manual](https://formdworks.com/products/manuals) to assemble it together. Assembly was surprisingly straightforward and clear, thanks to the manual. 

<figure class="third">
    <a href="/assets/images/posts/2022-09-18-building-a-sffpc/4.jpg"><img src="/assets/images/posts/2022-09-18-building-a-sffpc/4.jpg"></a>
    <a href="/assets/images/posts/2022-09-18-building-a-sffpc/21.jpg"><img src="/assets/images/posts/2022-09-18-building-a-sffpc/21.jpg"></a>
    <a href="/assets/images/posts/2022-09-18-building-a-sffpc/20.jpg"><img src="/assets/images/posts/2022-09-18-building-a-sffpc/20.jpg"></a>
    <figcaption>I did not yet install the panels, because I still have a computer I need to put in it!</figcaption>
</figure>

## Testing the Power Supply
I'm using a [Corsair SF750 power supply](https://www.corsair.com/us/en/Categories/Products/Power-Supply-Units/Power-Supply-Units-Advanced/SF-Series/p/CP-9020186-NA), which is probably the most popular ITX form factor PSU. Before assembling all my parts together, I tested the integrity of the PSU with a [PSU tester](https://www.amazon.com/gp/product/B076CLNPPK/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1), for my peace of mind. I connected the various pins from the PSU to the PSU tester, and checked that the voltage readings were all correct. 

![](/assets/images/posts/2022-09-18-building-a-sffpc/1.jpg)

## Assembling the Motherboard
I'm using an [AMD Ryzen 9 3900X](https://www.amd.com/en/product/8436) as my CPU with a [Gigabyte B550I Aorus Pro AX](https://www.gigabyte.com/Motherboard/B550I-AORUS-PRO-AX-rev-10/sp#sp) motherboard. 

<figure class="third">
    <a href="/assets/images/posts/2022-09-18-building-a-sffpc/2.jpg"><img src="/assets/images/posts/2022-09-18-building-a-sffpc/2.jpg"></a>
    <a href="/assets/images/posts/2022-09-18-building-a-sffpc/3.jpg"><img src="/assets/images/posts/2022-09-18-building-a-sffpc/3.jpg"></a>
    <a href="/assets/images/posts/2022-09-18-building-a-sffpc/7.jpg"><img src="/assets/images/posts/2022-09-18-building-a-sffpc/7.jpg"></a>
    <figcaption>I have some fan cables plugged in.</figcaption>
</figure>

For the CPU cooler, I'm opting for a [Noctua NH-L12 (Ghost S1 Edition)](https://noctua.at/en/nh-l12-ghost-s1-edition) air cooler. Installing the cooler on my AMD motherboard requires that I screw in AM4 brackets and spacers. 

<figure class="third">
    <a href="/assets/images/posts/2022-09-18-building-a-sffpc/9.jpg"><img src="/assets/images/posts/2022-09-18-building-a-sffpc/9.jpg"></a>
    <a href="/assets/images/posts/2022-09-18-building-a-sffpc/12.jpg"><img src="/assets/images/posts/2022-09-18-building-a-sffpc/12.jpg"></a>
    <a href="/assets/images/posts/2022-09-18-building-a-sffpc/15.jpg"><img src="/assets/images/posts/2022-09-18-building-a-sffpc/15.jpg"></a>
    <figcaption>I uninstall the hex standoffs that I had installed around the CPU, previously. Instead, I install the long AM4 brackets, so that the CPU cooler is oriented in such a way that it doesn't collide with the RAM and the motherboard's VRAM.</figcaption>
</figure>

I apply some CPU cooler---not too much though, because everyone on the internet likes to go on and on about how if you apply too much cooling paste, the cooling efficiency decreases. I then screw the CPU cooler in place above the CPU using a long screwdriver. 

<figure class="third">
    <a href="/assets/images/posts/2022-09-18-building-a-sffpc/16.jpg"><img src="/assets/images/posts/2022-09-18-building-a-sffpc/16.jpg"></a>
    <a href="/assets/images/posts/2022-09-18-building-a-sffpc/17.jpg"><img src="/assets/images/posts/2022-09-18-building-a-sffpc/17.jpg"></a>
    <a href="/assets/images/posts/2022-09-18-building-a-sffpc/18.jpg"><img src="/assets/images/posts/2022-09-18-building-a-sffpc/18.jpg"></a>
    <figcaption>The CPU cooler just barely makes clearance against some of the capacitors on the motherboard.</figcaption>
</figure>

We then place the motherboard into the case.

<figure class="third">
    <a href="/assets/images/posts/2022-09-18-building-a-sffpc/22.jpg"><img src="/assets/images/posts/2022-09-18-building-a-sffpc/22.jpg"></a>
    <a href="/assets/images/posts/2022-09-18-building-a-sffpc/23.jpg"><img src="/assets/images/posts/2022-09-18-building-a-sffpc/23.jpg"></a>
    <a href="/assets/images/posts/2022-09-18-building-a-sffpc/24.jpg"><img src="/assets/images/posts/2022-09-18-building-a-sffpc/24.jpg"></a>
    <figcaption>The FormD T1 includes some hex standoffs that raise the motherboard a little above the case skeleton. If you look carefully, you can see that the surface of the CPU cooler isn't actually parallel with the case---probably because the CPU cooler is pretty heavy. It doesn't bother me though.</figcaption>
</figure>

## Installing the Power Supply
Next, we install the power supply unit. The FormD T1 comes with a bracket for mounting the PSU. I use some screws to mount the PSU onto the bracket. 

<figure class="half">
    <a href="/assets/images/posts/2022-09-18-building-a-sffpc/26.jpg"><img src="/assets/images/posts/2022-09-18-building-a-sffpc/26.jpg"></a>
    <a href="/assets/images/posts/2022-09-18-building-a-sffpc/28.jpg"><img src="/assets/images/posts/2022-09-18-building-a-sffpc/28.jpg"></a>
    <figcaption>In the second photo, you can see the PCIe riser cable. I talk about installing the cable immediately below.</figcaption>
</figure>

## Installing the GPU

I then install the GPU. I'm using a [MSI RTX 3070 Ventus 2X](https://us.msi.com/Graphics-Card/GeForce-RTX-3070-VENTUS-2X-OC). 

![](/assets/images/posts/2022-09-18-building-a-sffpc/29.jpg)

30-series GPUs require a PCIe 4.0 connection, so I use a [Louqe Cobalt PCIe 4.0 riser cable](https://shop.louqe.com/products/cobalt-rc260-twinax-gen4-pci-e-4-0-riser-cable) to connect the GPU to the motherboard. I also use a threaded block that comes with the FormD case to secure the GPU to the PC case.

<figure class="third">
    <a href="/assets/images/posts/2022-09-18-building-a-sffpc/30.jpg"><img src="/assets/images/posts/2022-09-18-building-a-sffpc/30.jpg"></a>
    <a href="/assets/images/posts/2022-09-18-building-a-sffpc/32.jpg"><img src="/assets/images/posts/2022-09-18-building-a-sffpc/32.jpg"></a>
    <a href="/assets/images/posts/2022-09-18-building-a-sffpc/33.jpg"><img src="/assets/images/posts/2022-09-18-building-a-sffpc/33.jpg"></a>
    <figcaption>The first photo shows the end of the PCIe cable that connects to the GPU. The second photo shows the block that secures the GPU to the PC case. The final photo shows off the installed GPU.</figcaption>
</figure>

I then plugged in custom-length cables from [Pslate Customs](https://www.pslatecustoms.com/) into the PSU. 

<figure class="half">
    <a href="/assets/images/posts/2022-09-18-building-a-sffpc/34.jpg"><img src="/assets/images/posts/2022-09-18-building-a-sffpc/34.jpg"></a>
    <a href="/assets/images/posts/2022-09-18-building-a-sffpc/38.jpg"><img src="/assets/images/posts/2022-09-18-building-a-sffpc/38.jpg"></a>
    <figcaption>The custom-length cables going from the PSU to the motherboard.</figcaption>
</figure>

The GPU requires an adaptor that converts a 2x4 pin set into two 2x4 pin sets. 

<figure class="third">
    <a href="/assets/images/posts/2022-09-18-building-a-sffpc/35.jpg"><img src="/assets/images/posts/2022-09-18-building-a-sffpc/35.jpg"></a>
    <a href="/assets/images/posts/2022-09-18-building-a-sffpc/36.jpg"><img src="/assets/images/posts/2022-09-18-building-a-sffpc/37.jpg"></a>
    <a href="/assets/images/posts/2022-09-18-building-a-sffpc/38.jpg"><img src="/assets/images/posts/2022-09-18-building-a-sffpc/38.jpg"></a>
    <figcaption>The GPU adaptor cable.</figcaption>
</figure>

## Installing Exhaust Fans 
Proper cooling is critical for SFFPC builds. I installed two Noctua NF-A12x25 fans to the top of the case, so that they exhaust hot air from the inside of the PC to the outside. Installing the fans is straightforward. The Noctua fans come with self-tapping screws, and they secure the fans against some slots in the case. The two fans' cables are connected via a splitter, and the end of the splitter is plugged into `SYS_FAN1` on the motherboard. I also used some zip ties to clean up the cabling.

![](/assets/images/posts/2022-09-18-building-a-sffpc/44.jpg)

## Installing the Power Switch
The FormD T1 uses a very discrete button located on the side of the front panel to power on the machine. I find this button really unsatisfying to use, however, and even worse, I'm not always sure whether or not I've pressed it, because the button has very little tactility and travel distance. So I instead use this very discrete button as a resest switch, by plugging the leads into the reset pins on the motherboard. The motherboard's user manual identifies these pins.

{% include figure image_path="/assets/images/posts/2022-09-18-building-a-sffpc/pinout.png" caption="The polarity of the power switch and the reset switch do not matter. These switches just close or open the circuit."%} 

For the power button, I wanted to make use of the big M19 threaded holes at the back of the case. FormD actually sells M19 power switches on their online shop, but it's frequently out of stock. Fortunately, I found a M19 push button switch [on Amazon](https://www.amazon.com/gp/product/B017KPM0SC/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1) that works perfectly. The switch is supposed to light up as well, but I couldn't seem to get the LED working with the LED pins on the motherboard. 

<figure class="half">
    <a href="/assets/images/posts/2022-09-18-building-a-sffpc/46.jpg"><img src="/assets/images/posts/2022-09-18-building-a-sffpc/46.jpg"></a>
    <a href="/assets/images/posts/2022-09-18-building-a-sffpc/47.jpg"><img src="/assets/images/posts/2022-09-18-building-a-sffpc/47.jpg"></a>
    <figcaption>I soldered and heat shrunk the leads on the push button, and then screwed the button into one of the M19 threaded holes on the rear of the PC case.</figcaption>
</figure>

## Finishing Touches

Even though I couldn't get the LED that's built into the push button switch to work, I still wanted a power status LED. Fortunately, I have a bunch of LEDs lying around. I wired up a white LED to the motherboard's Power LED pins, and I Kapton taped it to the inside of the PC case's front panel. 

{% include figure image_path="/assets/images/posts/2022-09-18-building-a-sffpc/48.jpg" caption="It's a beautiful work of art."%} 

Finally, I wanted to do something about the other M19 threaded hole that's gaping open at the back of the case. The case has two M19 holes, and I used the power switch to cover one of the holes. Fortunately, FormD suplies [`.stl` files](https://formdworks.com/collections/t1-1/products/3d-files) for 3D-printing threaded caps that can cover the M19 holes. I found the dimensions of the threaded cap to be a little too snug, however, so I adjusted the file's x and y scaling in Prusa Slicer to 98%. With this slight adjustment, the print came out perfectly. 

![](/assets/images/posts/2022-09-18-building-a-sffpc/50.jpg)

## Fan Configuration

The PC is totally usable now! We can use it for all sorts of things, including more intense workloads like video games, CAD, and video editing work. Before we call it a day though, we're going to want to configure the fans. SFFPCs are small, and so they can build up a lot of heat inside the computer. We want to try and optimize the computer's cooling performance. 

By default, fans that are plugged into the motherboard will ramp up based on CPU temperature. So, the Noctua exhaust fans we installed will ramp up as the CPU temperatures get higher. We don't want this relationship, however. Instead, we want our exhaust fans to ramp up as the __GPU__ temperatures get higher. To estbalish this relationship, we have to use a program called [Argus Monitor](https://www.argusmonitor.com/). Optimum Tech shows how to use this program in [this video at 20:59](https://www.youtube.com/watch?v=Za0kx7hBeHc&t=1259s). 

{% include figure image_path="/assets/images/posts/2022-09-18-building-a-sffpc/argus.png" caption="My Argus Monitor settings. Recall that both my exhaust fans are plugged into `SYS_FAN1` via a fan splitter. So we have one fan port controlling two fans."%} 

## GPU Undervolting

Everyone in the SFFPC world recommends undervolting the GPU. Undervolting the GPU results in quieter and cooler operation, with no cost to performance. Again, Optimum Tech explains how to undervolt the GPU in [this video at 21:36](https://www.youtube.com/watch?v=Za0kx7hBeHc&t=1296s). We use a software called [MSI Afterburner](https://afterburners-msi.com/en/Afterburner.html?gclid=CjwKCAjwg5uZBhATEiwAhhRLHv5LlaFr85ASJFyvH_DIyTouc8-LeeGJDlb4gv8D9ItCsIutwv04_xoC9mYQAvD_BwE) to undervolt the GPU.

{% include figure image_path="/assets/images/posts/2022-09-18-building-a-sffpc/undervolt.png" caption="My GPU undervolt curve in MSI Afterburner."%}

## Future Improvements

All in all, I'm very happy with the build! I think the only thing I might want to add in the future is a [front IO panel](https://formdworks.com/collections/t1-1/products/usb-c-front-io-kit).

<figure class="half">
    <a href="/assets/images/posts/2022-09-18-building-a-sffpc/49.jpg"><img src="/assets/images/posts/2022-09-18-building-a-sffpc/49.jpg"></a>
    <a href="/assets/images/posts/2022-09-18-building-a-sffpc/51.jpg"><img src="/assets/images/posts/2022-09-18-building-a-sffpc/51.jpg"></a>
    <figcaption>You can see the white power LED glowing in the second picture.</figcaption>
</figure>
## Parts Summary

| Item         | Part                                                         |
| ------------ | ------------------------------------------------------------ |
| Case         | [FormD T1 Sandwich Kit](https://formdworks.com/products/t1-sandwich-kit-black-color) |
| PSU          | [Corsair SF750 power supply](https://www.corsair.com/us/en/Categories/Products/Power-Supply-Units/Power-Supply-Units-Advanced/SF-Series/p/CP-9020186-NA) |
| CPU          | [AMD Ryzen 9 3900X](https://www.amd.com/en/product/8436)     |
| CPU Cooler   | [Noctua NH-L12 (Ghost S1 Edition)](https://noctua.at/en/nh-l12-ghost-s1-edition) |
| Motherboard  | [Gigabyte B550I Aorus Pro AX](https://www.gigabyte.com/Motherboard/B550I-AORUS-PRO-AX-rev-10/sp#sp) |
| RAM          | [Corsair Vengeance LPX 64GB (2 x 32GB) DDR4 DRAM 3200MHz](https://www.corsair.com/us/en/Categories/Products/Memory/VENGEANCE-LPX/p/CMK64GX4M2E3200C16) |
| SSD          | [Samsung 970 Evo Plus 1 TB](https://www.samsung.com/us/computing/memory-storage/solid-state-drives/ssd-970-evo-plus-nvme-m-2-1-tb-mz-v7s1t0b-am/) |
| GPU          | [MSI RTX 3070 Ventus 2X](https://us.msi.com/Graphics-Card/GeForce-RTX-3070-VENTUS-2X-OC) |
| PCIe riser   | [Louqe PCIe 4.0 riser cable](https://shop.louqe.com/products/cobalt-rc260-twinax-gen4-pci-e-4-0-riser-cable) |
| Exhaust Fans | Two [Noctua NH A12x25  fans](https://noctua.at/en/nf-a12x25-pwm) |
| Power Switch | [Ulincos Momentary Pushbutton Switch U19D1 1NO SPST for 19 mm mounting hole](https://www.amazon.com/gp/product/B017KPM0SC/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1) |

## Footnotes

[^1]: You can still build very poweful computers in ITX cases, without creating the world's desnsest space heater. In many ways, the engineering challenge of trying to build the most powerful computer in the smallest space is what draws people into the SFFPC world. People have come up with clever ways of efficiently disippating heat from even the most power hungry hardware. 
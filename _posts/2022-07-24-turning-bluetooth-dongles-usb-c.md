---
title: Turning Bluetooth Dongles into USB-C
header:
    header: /assets/images/posts/2022-07-24-making-bluetooth-dongles-usb-c/final-dongle.png
    teaser: /assets/images/posts/2022-07-24-making-bluetooth-dongles-usb-c/final-dongle.png
    og_image: /assets/images/posts/2022-07-24-making-bluetooth-dongles-usb-c/final-dongle.png
    overlay_image: /assets/images/posts/2022-07-24-making-bluetooth-dongles-usb-c/final-dongle.png
    overlay_filter: rgba(103, 110, 149, 0.30)
excerpt: ":sweat: Why are there no USB-C dongles?!"
tags: 
    - Builds
---

2.4 GHz Bluetooth USB dongles never seem to be USB-C. I find this dearth a bit annoying, because my MacBook Pro features only USB-C ports, and it seems silly that I'd have to carry around an awkward USB to USB-C port, if I ever wanted to use a Bluetooth dongle with my MacBook. 

Fortunately, the popular YouTube channel, [DIY Perks](https://www.youtube.com/channel/UCUQo7nzH1sXVpzL92VesANw), noticed the same issue, and made a whole video about converting USB devices to USB-C:

{% include video id="V-vFtiDYiIw" provider="youtube" %}

I thought this tutorial would be perfect for my TU40 v3 keyboard, which has a 2.4 GHz Bluetooth dongle that connects via USB 2.0. In this post, I describe how I convert my keyboard's Bluetooth dongle to USB-C, based on the DIY Perks video, above. 

{% include figure image_path="/assets/images/posts/2022-07-24-making-bluetooth-dongles-usb-c/tu40-dongle.png" alt="" caption="A USB 2.0 dongle? Gross! An adaptor? Also gross!"%}

As is usually the case with these kinds of projects, I wasn't able to get the exact USB-C breakout board that DIY Perks recommends, so I had to make some slight hardware adjustments, based on what's available to me. First, I bought the male USB-C breakout board off Amazon (ASIN: [B09WCQKSW1](https://www.amazon.com/dp/B09WCQKSW1?ref=ppx_yo2ov_dt_b_product_details&th=1)). The PCB I bought doesn’t have all the USB-C pins broken out. Rather, it just has the four main pins typical of USB 2.0 cables, broken out: V, D+, D-, and GND. By convention, V is red, GND is black, D+ is green, and D- is white. This USB-C breakout board, like almost all USB-C breakout boards, is configured as a _host_ device. Even though I shouldn't have felt surprised by this revelation, I was a little miffed because the Amazon photos for the product clearly show the PCB hardware-configured _not_ as a host device:

{% include figure image_path="/assets/images/posts/2022-07-24-making-bluetooth-dongles-usb-c/amazon-stock.png" alt="" caption="<b>Photo from the Amazon product page.</b> The product page photo has the R1 resistor soldered in, which on this PCB, would pull down the voltage, and put the USB device into sub-device mode. In reality, the PCBs I got were configured in host device mode. In addition, the PCBs I got did not have a capacitor on the C1 pad—I don’t think that should make a difference though."%}

We want to configure the board as a _sub-device_, however, because we wish to use it as a receiver for a mechanical keyboard. To do so, we have to alter the host device configuration, which is defined by the implementation of pull-up resistor, to a sub-device configuration, which is defined by the implementation of a pull-down resistor. To see how we do this, let’s examine the pinout of USB-C:

{% include figure image_path="/assets/images/posts/2022-07-24-making-bluetooth-dongles-usb-c/usb-c-pinout.png" alt="" caption="<b>USB Type-C pinout.</b> Notice how the pinout is more or less rotationally symmetric. The pin we really care about is the CC1 pin. Whether the CC1 pin is configured with a pull-up or a pull-down is what defines the USB-C connection as a host device, or a sub-device, respectively. "%}

Like I mentioned already, a pull-up configuration configures the USB-C connection as a host device. In other words, a USB-C connection as a host device has the following: 

{% include figure image_path="/assets/images/posts/2022-07-24-making-bluetooth-dongles-usb-c/usb-c-pullup.png" alt="" caption="A resistor pulls up the CC1 pin to the logic voltage, VBUS (V)."%}

If we examine our PCB closely, the CC1 pin is indeed pulled up:

{% include figure image_path="/assets/images/posts/2022-07-24-making-bluetooth-dongles-usb-c/usb-c-closeup-photo.png" alt="" caption="We have a resistor on R2. If we trace the copper traces of R2, we can see that one trace goes to the 4th pin from the left, which is the VBUS. The fact that a resistor goes to the VBUS, probably means it’s the resistor that configures the USB-C connection as a host device. "%}

So we need to remove the resistor, R2, that is responsible for the pull-up and the host device configuration. In the DIY Perks video, Matt scrapes off a trace that goes from the pull-up resistor. I found this method to be pretty obnoxious, and Reddit actually suggested that it’d be better for me to completely desolder the pull-up resistor on R2: 

![](/assets/images/posts/2022-07-24-making-bluetooth-dongles-usb-c/reddit-post.png)

Desoldering the resistor was easy enough!

{% include figure image_path="/assets/images/posts/2022-07-24-making-bluetooth-dongles-usb-c/no-resistor.png" alt="" caption="R2 now does not have a resistor."%}

We must now implement the pull-down resistor onto the CC1 pin:

{% include figure image_path="/assets/images/posts/2022-07-24-making-bluetooth-dongles-usb-c/usb-c-pulldown.png" alt="" caption="A resistor pulls down the CC1 pin onto the GND pin."%}

To do so, I solder in a 4.7 kOhm resistor from GND to the CC1 pin, like they do in the video. 

<figure class="half">
    <a href="/assets/images/posts/2022-07-24-making-bluetooth-dongles-usb-c/pulldown-top.png"><img src="/assets/images/posts/2022-07-24-making-bluetooth-dongles-usb-c/pulldown-top.png"></a>
    <a href="/assets/images/posts/2022-07-24-making-bluetooth-dongles-usb-c/pulldown-bottom.png"><img src="/assets/images/posts/2022-07-24-making-bluetooth-dongles-usb-c/pulldown-bottom.png"></a>
    <figcaption><b>Left:</b> We know that the R1 pad we soldered onto (the one on the left) is the CC1 pin, because the pad on the right has a copper trace that clearly goes to the far right USB-C pin, which is the GND pin. Therefore, the left pad, must be the CC1 pin. So we solder our resistor onto there. The other end of the resistor is soldered onto the GND pin that’s on the opposite side of the PCB, because it’s easier to solder the through-hole resistor onto that pad, rather than the opposing (right) R1 pad. <br/><b>Right</b>: The opposite side of the USB-C PCB has pins that are clearly labelled as G, D+, D-, and V. So we know to put the other lead of the pull-down resistor onto the big GND pad here. (This image was taken before I soldered the pull-down resistor onto the GND pad).  </figcaption>
</figure>

:bulb: **FYI** :bulb:: If I was really precise, I would solder the resistor that was on R2, onto R1—this modification would be the cleanest way of configuring the USB-C connection to sub-device mode. But admittedly, I didn’t have this idea until after I completed the project.
{: .notice--info}

We’re done doing the most finicky soldering work! Now we just need to connect the G, D+, D-, and V pins to the Bluetooth module. To do this, we first need to open up the Bluetooth module. I use a pair of needle-nose pliers: 

<figure class="half">
    <a href="/assets/images/posts/2022-07-24-making-bluetooth-dongles-usb-c/dongle.png"><img src="/assets/images/posts/2022-07-24-making-bluetooth-dongles-usb-c/dongle.png"></a>
    <a href="/assets/images/posts/2022-07-24-making-bluetooth-dongles-usb-c/dongle-pryed.png"><img src="/assets/images/posts/2022-07-24-making-bluetooth-dongles-usb-c/dongle-pryed.png"></a>
    <figcaption>A trusty pair of needle-nose pliers will make quick work of the metal casing around the dongle's PCB.</figcaption>
</figure>

{% include figure image_path="/assets/images/posts/2022-07-24-making-bluetooth-dongles-usb-c/dongle-apart.png" alt="" caption="All the parts of the Bluetooth receiver taken apart."%}

Next, we’re going to want some thin wires. Rather than purchase a bunch of such wires, the DIY Perks video cleverly suggests just stripping some old USB cable. 

<figure class="half">
    <a href="/assets/images/posts/2022-07-24-making-bluetooth-dongles-usb-c/usb-cable.png"><img src="/assets/images/posts/2022-07-24-making-bluetooth-dongles-usb-c/usb-cable.png"></a>
    <a href="/assets/images/posts/2022-07-24-making-bluetooth-dongles-usb-c/usb-cable-stripped.png"><img src="/assets/images/posts/2022-07-24-making-bluetooth-dongles-usb-c/usb-cable-stripped.png"></a>
    <figcaption>Cut the cable with some wirecutters. Then, strip the cable with some wire-strippers to reveal four wires and some shielding.</figcaption>
</figure>

Now we just need to solder the wires together. Our USB-C breakout board has very clearly labelled pads, for GND, D+, D-, and V, so wiring those pads up is easy. The Bluetooth PCB that has the original USB-A port will, by definition, have its stereotypically shaped 4 pads in the following orientation:

{% include figure image_path="/assets/images/posts/2022-07-24-making-bluetooth-dongles-usb-c/dongle-pinout.png" alt="" caption="These pads are labelled in the above order, by definition."%}

Once we solder those wires together, we’re all done with the electronics!

<figure class="half">
    <a href="/assets/images/posts/2022-07-24-making-bluetooth-dongles-usb-c/assembly-top.png"><img src="/assets/images/posts/2022-07-24-making-bluetooth-dongles-usb-c/assembly-top.png"></a>
    <a href="/assets/images/posts/2022-07-24-making-bluetooth-dongles-usb-c/assembly-bottom.png"><img src="/assets/images/posts/2022-07-24-making-bluetooth-dongles-usb-c/assembly-bottom.png"></a>
    <figcaption>I added some hot glue, to prevent some of the exposed metal contacts from touching each other, when they get scrunched up.</figcaption>
</figure>

We then add some Sugru to cover up the bare electronics (or if you’d like, 2-part epoxy), and wait about 24 hours for the Sugru to dry! 

{% include figure image_path="/assets/images/posts/2022-07-24-making-bluetooth-dongles-usb-c/final-dongle.png" alt="" caption="You can see some fingerprints on the Sugru, but those can be smoothed out with angled tweezers, or any kind of flat edge. I’ve also depicted here a connected female USB-C port, so that when molding the Sugru in place, I know how much minimum space I should leave in order for the male USB port to remain physically functional."%}

Here’s a video of the operational USB-C receiver! I replaced the grey Sugru casing for a black one! 

{% include video id="MLZ67qd8cs0" provider="youtube" %}
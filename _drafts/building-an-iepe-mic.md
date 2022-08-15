---
title: Building an IEPE Microphone for Data Collection
header:
    header: /assets/images/posts/2022-08-14-iepe-mic/mounted-pcb.jpg
    teaser: /assets/images/posts/2022-08-14-iepe-mic/mounted-pcb.jpg
    og_image: /assets/images/posts/2022-08-14-iepe-mic/mounted-pcb.jpg
    overlay_image: /assets/images/posts/2022-08-14-iepe-mic/mounted-pcb.jpg
excerpt: ":microphone: Build a MEMs-based IEPE-powered instrumentation microphone!"
tags:
    - Builds
    - HIDs
---

I saw [this project](https://hackaday.io/project/185762-mems-based-iepe-powered-instrumentation-microphone) on Hackaday, and thought a) wow, that's pretty cheap!, and b) having multiple microphones that can synchronize against a DAQ (data acquisition) device could be a fun way of getting high-quality acoustic data[^1] that lends itself to all sorts of fun analyses[^2]. In this post, I detail my build log of MEMS (micro-electromechanical)-based IEPE (integrated electronics piezo-electric)-powered microphones.

## Theory

## Build
I started by printing the microphone case. The case is dead simple---it has a top half, and a bottom half. The two parts don't fit together super well, but I figured I'd cross that bridge when I got there. 

I moved onto the electronics. The microphone has two PCBs. One is the 'motherboard', and it carries the amplifiers, voltage regulators, some resistors and capacitors, and the male BNC jack. The other board contains only the MEM components. The two boards connect via 30 AWG silicone wires. 
I ordered the PCBs, with some of the components pre-populated from [JLCPCB](https://jlcpcb.com/).[LCSC](https://lcsc.com/) (the company JLCPCB uses to source their components for PCB population) didn't have any sufficient alternatives for some of the components, however, and so those could not be factory-populated. Instead, I had to order those parts myself, and solder them onto the boards. Namely, I had to source and solder the op amps, voltage regulators, and 100 nF ceramic caps, I sourced the op amps and the caps from [Mouser Electronics](https://www.mouser.com/), but I couldn't find any of the exact voltage regulators (TLVH432ACDBZR), from any vendor, including Texas Instruments. I realized later though (and the creator of the project, Peter Riccardi confirmed this fact), that I could replace the out-of-stock part with a cclosely related [in-stock part](https://www.mouser.com/ProductDetail/595-TLVH432BCDBZR) (TLVH432BCDBZR), because the only difference between the two parts is that the initial voltage range of the in-stock part is slightly more accurate---so if anything, it's a bit of an upgrade, I guess! 

I already had some screw terminal BNC connectors, so I figured I should try to detach the screw terminals from the BNC connectors, as a way of saving both time and money. I clamped the BNC connector onto my vice, and used a pair of needle-nose pliers to yank out the rubber mount that affixed the screw terminals onto the BNC connection. 

<figure class="third">
    <a href="/assets/images/posts/2022-08-14-iepe-mic/detach-bnc-0.jpg"><img src="/assets/images/posts/2022-08-14-iepe-mic/detach-bnc-0.jpg"></a>
    <a href="/assets/images/posts/2022-08-14-iepe-mic/detach-bnc-1"><img src="/assets/images/posts/2022-08-14-iepe-mic/detach-bnc-1.jpg"></a>
    <a href="/assets/images/posts/2022-08-14-iepe-mic/detach-bnc-2.jpg"><img src="/assets/images/posts/2022-08-14-iepe-mic/detach-bnc-2.jpg"></a>
    <figcaption>The process by which I separated the screw terminals from the BNC connector.</figcaption>
</figure>

Once the PCBs and all the parts came in, I got to soldering! All the parts are super small SMDs, and in the case of the MEMs, the solder pads were located underneath the components, such that a soldering iron couldn't even access the pads! I had heard that for SMD soldering, a temperature-controlled heat gun is the way to go, and so I purchased the cheapest one I could find, off Amazon. I then soldered all the pieces onto the board with the heat gun, a syringe, and some solder paste. The heat gun soldering process is quite magical. Everything kind of just slips into place :astonished:. 

For all the components, except for the op amps, their orientations on the board either didn't matter (the ceramic caps and resistors), or they were defined in such a way that only one orientation was possible (the voltage regulators). In the case of the op amps, I needed to look closely at their top surface, for a notch that indicated the position of pin 1. 

{% include figure image_path="/assets/images/posts/2022-08-14-iepe-mic/amp-orientation.jpg" alt="" caption="The red arrow shows the horizontal line that indicates the placement of the op amp's pin 1. A look at the part's [datasheet](https://www.ti.com/lit/ds/symlink/tlv9101.pdf?ts=1660518474300&ref_url=https%253A%252F%252Fwww.google.com%252F) (page 4) shows that pin 1 is on the left side of the horizontal line. The motherboard PCB features a white dot that indicates pin 1. With all this information, we can properly align the op amp onto the PCB."%}

All in all, the soldering process was pretty smooth! The populated PCBs look quite nice, altogether:

![](/assets/images/posts/2022-08-14--iepe-mic/soldered-boards.jpg)

Now, I needed to hook up the two PCBs together, via the 30 AWG wire. Unfortunately, a hook-up guide didn't exist on the Hackaday article. I tried to piece things together, but I didn't understand the electronics well enough to make sense of what was going on. So I messaged Peter on Hackaday, and he was the most helpful and friendliest person ever! He quickly got me out of the mud. I needed to hook up the boards like so:

{% include figure image_path="/assets/images/posts/2022-08-14-iepe-mic/hookup.jpg" alt="" caption="'MOBO' refers to the 'motherboard', i.e. the bigger PCB. 'CARRIER' refers to the board with the actual MEMs, i.e. the smaller PCB."%}

I needed a little foresight, with regards to the BNC connector. That is, I had to solder the leads onto the BNC, _after_ having threaded the leads through the BNC opening of the case's bottom half. Otherwise, there's no way to fit the electronics inside the case. 

{% include figure image_path="/assets/images/posts/2022-08-14-iepe-mic/solder-after-looping.jpg" alt="" caption="I hadn't yet soldered the negative lead (the lead that hasn't yet slipped through the BNC opening) onto the PCB, and so I didn't have to cut the wire, slip it, and then splice it back together again. Thank goodness."%}

Then, I press fit the BNC connector into the case's BNC opening. It took a little bit of force, but then it snapped in place, pretty well. 

![](/assets/images/posts/2022-08-14-iepe-mic/press-fit-bnc.jpg)

The microphone is beginning to shape up! I need only to fit the top half of the case. 

![](/assets/images/posts/2022-08-14-iepe-mic/mounted-pcb.jpg)

## Footnotes
[^1]: I.e. typing sounds on different keyboards
[^2]: E.g. Spectrogram profiles and decompositions. In the case of keyboard typing sounds, I can try and write a decoder that predicts the switch type (linear vs. tactile), mounting type, case material, foam materials, etc.. 
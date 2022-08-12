---
title: Building a Gasket-Mounted Let's Split Keyboard
excerpt: ":dancing_women: Yet another keyboard build! I make this keyboard gasket-mounted!"
tags:
    - HIDs
    - Builds
# header:
#     og_image: /assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/16.jpg
#     teaser: /assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/16.jpg
#     header: /assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/16.jpg
#     overlay_image: /assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/16.jpg
---

In this post, I document my build of the [Let's Split (v2)](https://github.com/climbalima/let-s-Split-v2) keyboard. It's basically a split version of the beloved Planck keyboard, and its various incarnations. A newer and improved version of the Let's Split (V2) keyboard---called the Levinson---exists, but it's not open-sourced :angry:. Oh well, the Let's Split (v2) is still awesome! The PCB is reversible, so the same PCB is used for both sides of the split keyboard. The µCs and TRRS jacks are on the _bottom_ of the keyboard.  

## Electronics
For setting up the electronics, I heavily referenced [this guide](https://github.com/nicinabox/lets-split-guide). If you need more informative imgages, I recommend the guide. 

1. **Connect the µCs**. I'm using two [Bit-C](https://nullbits.co/bit-c/)s as my µCs. I'm also using the [low-profile Mill-Max sockets](https://www.digikey.com/en/products/detail/mill-max-manufacturing-corp/115-93-624-41-003000/81896) and their [corresponding pins](https://www.digikey.be/en/products/detail/mill-max-manufacturing-corp/3320-1-00-15-00-00-03-0/4147393). I solder these parts, as usual. 

    {% include figure image_path="/assets/images/posts/2022-08-08-building-a-lets-split-kbd/0.jpg" caption="I found that each Mill-Max pin is exactly the length for two sockets. So I put the pins on every other socket hole, soldered them to the µC, and then snipped the extra pin lengths with flush cutters, while holding the extra lengths with needle-nose pliers. This way, the cut pins lengths don't fly away."%}

2. **Solder the TRRS jack connectors**. The PCB features 6 holes (because the PCB is reversible), but we need only make four connections, as is typical of TRRS connections. Connect the TRRS jacks to the PCBs, via the connections shown below. 

    {% include figure image_path="/assets/images/posts/2022-08-08-building-a-lets-split-kbd/1.jpg" caption="Identical colours indicate connections between the the TRRS jack pins and the PCB through-holes."%}

    The photo below shows the keyboard, so far, with its bottom side facing up. So the left half is shown on the right, and the right half is shown on the left. 

    ![](/assets/images/posts/2022-08-08-building-a-lets-split-kbd/2.jpg)

3. **Short jumpers**. We need to short some jumpers. Doing so will electrically 'orient' the keyboard, and define each half as either left or right. This step is necessary, because of the PCB's reversible nature. 

    {% include figure image_path="/assets/images/posts/2022-08-08-building-a-lets-split-kbd/3.jpg" caption="The shorted pads are indicated with red rectangles."%}

4. **Connect diodes and resistors**. We polarize the keyboard matrix circuit with 1N4148 diodes, like we would with pretty much any keyboard. We also solder two 4.7 kΩ resistors on _any one_ of the two PCBs---it doesn't matter which PCB gets the two resistors, and it's ok, but unnecessary, if both PCBs get the resistors. The resistors are required for setting an I2C protocol on the keyboard, as opposed to serial. I2C has the advantage of [being lower latency, and it allows either PCB to act as 'master'](https://www.reddit.com/r/MechanicalKeyboards/comments/66xc6e/help_lets_split_serial_vs_i2c/). If you're not using LED strips (:dizzy_face:), you should use I2C.  

    {% include figure image_path="/assets/images/posts/2022-08-08-building-a-lets-split-kbd/4.jpg" caption="Only one PCB needs the two 4.7 kΩ resistors. Ignore the one diode I didn't solder . . . I got to that one later."%}

5. **Short the I2C jumpers**. On the one side of the PCB, short the I2C jumper pads, for _both PCBs_. These pads are located beneath the D17 diode. 

    ![](/assets/images/posts/2022-08-08-building-a-lets-split-kbd/5.jpg)



## Case

## Finishing Touches

## Future Improvements
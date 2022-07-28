---
title: Modding a Cheap Keyboard
tags:
    - HIDs
    - Builds
excerpt: "Giving a cheap keyboard a makeover!"
---
Some close friends of mine own a cheap Velocifire TKL61WS mechanical keyboard. Since they first purchased this keyboard, they've gone deep down the mk rabbit hole (of which, I obviously had nothing to do with ...), and no longer feel very impressed with the keyboard. I thought it might be a fun project and gift if I modded it for them. This blog post details my modding adventures. 

## Disassembly

Here's a photo of the original keyboard with some of its default keycaps still in place. Something of a looker, but not necessarily in the best way:

{% include figure image_path="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/original.jpg" alt="" caption="Not the most handsome fellow in the world. It also sounds awful. If I owned a decent mic, I'd try and record the typing sound, just for comparison with an 'after' video ... but perhaps it's a small fortune that I can't share its original sound profile with the world, haha. We're going to try and change all that though. It's makeover time!"%}

We start by unscrewing all the screws on the switch plate, which is what's affixing the plate and the PCB onto the case.

<figure class="half">
    <a href="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/unscrewed.jpg"><img src="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/unscrewed.jpg"></a>
    <a href="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/jst-cable.jpg"><img src="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/jst-cable.jpg"></a>
    <figcaption>Yum, stock Gateron browns :woozy_face:. There's a 1800 mAh 3.7 V battery though! That's a decent amount of juice. It's connected to the PCB via a 2-pin JST cable. Gotta unplug that sucker.</figcaption>
</figure>

We now need to remove the switches from the PCB. Technically, there are these small 'hot-swap sockets' installed onto the PCB (which were not Kailh styles, but were rather low quality Mill-Max style clones), and they had a kind of death grip on the Gateron brown switches. I think these sockets are awful, and I made an executive call to just destroy them, and turn the board into a dependable solder-only board :smile:. 

{% include figure image_path="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/desoldering-1.jpg" alt="" caption="It's a little hard to tell from this photo, but the hot-swap sockets are preventing the desoldering gun from coming in direct contact with the PCB at the level of the FR4. So we're going to use flush cutters. "%}

Getting rid of the sockets requires us to snip off the backside of the switch leads with flush cutters, because the added thickness from the sockets are preventing my desoldering gun from getting a good grip on the leads. 

{% include figure image_path="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/snip-off.jpg" alt="" caption="Gotta cut those leads off so my desoldering gun can get a good suction!"%}

After a decent amount of work, I've desoldered all 2 billion switches:

{% include figure image_path="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/desoldered.jpg" alt="" caption=""%}

And I've had to sacrifice those juicy Gateron brown switches in the process. Can't say they'll be missed! :grin:

{% include figure image_path="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/gross-gat-browns.jpg" alt="" caption=""%}

I did notice two unusual features about the board, after I desoldered all the switches. One is that the stabilizers appear to be integrated into the _switch plate_ rather than the PCB, which is definitely atypical. So I'm guessing that means I can't upgrade the stabs to something like Owlab or Durock stabs. It does mean that I'll still be able to [holee mod](https://www.youtube.com/watch?v=-vhpHjlkRgQ) and lube the stabs though. 

The other is that there appears to be a 'grounding' spring on the PCB. It seems to line up directly with an exposed metal contact on the switch plate. Personally, I find this feature to be a little strange ... from an acoustic perspective at least, the direct contact of the metal spring onto the metal switch plate is going to result in a lot of pinging sounds. I've also just never seen this feature before, and I've worked with keyboards with metal switch plates. I think I'm going to desolder the spring and add some padding between the switch plate and the PCB (especially on the exposed part of the plate that's meant to contact the spring) to a) dampen any kind of unwanted pinging noise, and b) prevent any kind of electrical conductivity between the plate and the PCB. 

{% include figure image_path="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/grounding-spring.jpg" alt="" caption="I've circled in blue the spring and the exposed part of the switch plate that lines up directly with the spring top. I'm pretty sure it's a grounding thing, because we can see that the spring is soldered onto the PCB. "%}

## Add Some Foam between the Switchplate and the PCB

On that note, I decided to cut some [double-sided grippy tape](https://www.amazon.com/gp/product/B07VNSXY31/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1) to dampen the switch plate-PCB interface sound. 

{% include figure image_path="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/padded-switchplate.jpg" alt="" caption="It looks a little ugly, but it definitely gets the job done. No one's going to see the guts anyway."%}

I also added a thin layer of PE foam between the PCB and the underside of the doublde-sided grippy tape. When I install the switches, their conductive pins will poke right through the PE foam, and make contact with their corresponding PCB sockets. You'll see what I mean, once I get around to [installing the switches](#add-decent-switches). 

## Mod the Stabilizers

Nothing fancy here. Just some typical [holee modding](https://www.youtube.com/watch?v=-vhpHjlkRgQ) and lubing with Krytox 205G0. 

{% include figure image_path="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/holee-modded.jpg" alt="" caption="Some holee modded-stabs. You can see the cut band-aids sticking out from the stab insides."%}

Like I mentioned above, the stabs are quite strange in that they clip onto the switchplate, rather than the PCB. This trait didn't have too much effect on my modding, though, aside from the fact that the switch plate's grippy tape 'foam' would sometimes interfere with the motion of the stabilizer bars. To get around the issue, I removed the grippy tape from the parts of the switch plate that were close to the stab bars. 

{% include figure image_path="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/removing-bad-grippy-tape.jpg" alt="" caption="Peeling off the grippy tape strips that interfered with the stabilizer bars."%}

I then pressed the stabilizer-supported keys a bunch, to check that they were moving ok. Things seemed to be going not so bad, so far!

## Add Decent Switches
During my disassembly process, I wound up getting rid of the crappy little hot-swap sockets (which were not Kailh-style, but were rather, low quality Mill Max-style). So the keyboard is now a solderable board, which I think is for the best, because the existing hot-swap sockets were already fraying, perhaps in part due to the shoddy PCB fabrication. Given that the keyboard is no longer hot-swap, I figured I should pick a decent set of switches, because they'll probably be there a while.

I wound up picking the [JWK Jwick Linear Reds (62 g)](https://divinikey.com/products/jwk-jwick-linear-switches?variant=39897727893569), because they're nice stock switches that don't need to be lubed, and come at a really great price, at $0.23 USD / switch.  

{% include figure image_path="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/red-jwicks-stock.webp" alt="" caption="**JWK Jwick linear reds**: 62 g springs, polycarbonate top housing, nylon PA66 bottom housing, and POM stems."%}

I realized after the switches came in, however, that the PCB accepted only 3-pin switches and not 5-pin switches (the term 'pin' here is kind of silly, because three of the 'pins' are just plastic protorusions that help secure the switch, but everyone in keyboard land just calls them 'pins'). So I had to cut the two plastic legs off each Jwick, so that they effectively became 3-pin switches. The switches still weren't fitting into the PCB though, and I realized that not only were the keyboard's original Gateron Browns 3-pins, but they also possessed a large cavity at the back of the switch, so that the PCB's RGB lights could shine behind each alpha key. The Jwiks did not have such a cavity, however, and so they refused to sit flush against the PCB, while the LEDs were still there. 

{% include figure image_path="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/i-hate-this-pcb.jpg" alt="" caption="This PCB seems to have a lot of features that express its hatred for decent keyboard switches. It has tacky RGB LEDs, and is misisng 5-pin switch support, both of which prevent the new switches from sitting flush against the PCB."%}

<figure class="half">
    <a href="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/switch-comparison-front.jpg"><img src="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/switch-comparison-front.jpg"></a>
    <a href="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/switch-comparison-bottom.jpg"><img src="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/switch-comparison-bottom.jpg"></a>
    <figcaption>I didn't notice it at first, but the original Gateron Browns were 3-pin switches that also possessed a cavity, which is an unusual way of supporting RGB LEDs.</figcaption>
</figure>

Fortunately, my friends and I hate RGB, so I soldered those right off. 

{% include figure image_path="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/desoldered-leds.jpg" alt="" caption="**The results of my LED desoldering job.** I used a heat gun to desolder the LEDs, and in the process, I usually wound up melting the LED casing. So they were not exactly usable upon removable, which was my initial hope."%}

Finally, I was ready to install the switches and solder them in place. This part went very smoothly, and was quite relaxing.

<figure class="half">
    <a href="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/install-some-switches.jpg"><img src="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/install-some-switches.jpg"></a>
    <a href="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/install-all-switches.jpg"><img src="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/install-all-switches.jpg"></a>
    <figcaption><b>The switch installation process.</b> You can see the PE foam underneath the switch plate. I just had to poke the switches through, then solder them in place.</figcaption>
</figure>

Then, I put on the keycaps. It's almost impossible to mess this part up. I'm using some cheap [Modern Dolch Light PBT clones I picked off of Amazon](https://www.amazon.com/gp/product/B08BKS31JZ/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1), some time ago. 

{% include figure image_path="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/keycaps.jpg" alt="" caption="All the keycaps are in place! I like this colour scheme a lot."%}

## Undo Mistakes

It turns out that when I was removing the cheap 'hot-swap' switch sockets during the [disassembly](#disassembly) process, I also removed the PCB's copper tracing along certain switch footprints on the PCB. I shouldn't have been too surprised about this wrinkle, given the general quality of the PCB, but I felt like it still could have been avoided. I took me more time than I'd like to admit to figure out the [keyboard matrix circuit](https://en.wikipedia.org/wiki/Keyboard_matrix_circuit) on this PCB, but I got it [eventually](keyboardtester.com/tester.html), and I used some thin wires to re-establish the lost connections.

{% include figure image_path="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/my-mistakes.jpg" alt="" caption="**My repairs**. I used six pieces of 30 AWG wire to reconnect the traces that I broke off with my somewhat aggressive desoldering."%}

## Remove Ugly Silkscreen Logo

The keyboard's original case has a really ugly logo that loudly reads "Velocifire" on its front. I got rid of it with some nail polish remover (acetone) and a lint-free cloth. The case is made of ABS plastic, so acetone also has a smoothing effect on the case. 

{% include figure image_path="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/acetone-cleaning.jpg" alt="" caption="What the case looks like, while in the middle of acetone cleaning. You can see a faint bit of the logo still left on the front of the case."%}

## Add a Gasket Mount

The way a keyboard is mounted is critical to its typing feel and sound. I think a fantastic and straightforward way of mounting a keyboard's PCB and switch plate to the case is via a soft o-ring gasket. This strategy was made famous by the [Bakeneko 60](https://github.com/kkatano/bakeneko-60), and I've also used it myself for my ['Planckeneko'](https://github.com/hanhanhan-kim/kbd-cases) project. I got the idea of using an o-ring gasket mount as a part of a modding-on-the-cheap project from one of my fave keyboard YouTube channels, [Keybored](https://www.youtube.com/c/Keybored):

{% include video id="zt-WsH7Z9c8" provider="youtube" %}

I think I'm going to take the same approach as the video, and saw off the original plastic standoff mounts, so that they no longer provide any mounting contacts, and all contacts are done via the gasket instead. 

## Make it QMK-Programmable

I own a Hasu USB-USB converter, from back when I first got started in the hobby. I don't use it anymore, because I don't like boards that aren't natively programmable, but I think it might just the thing for this modding project. I recall my friends mentioning how confusing it is to access the arrow keys with the Velocifire's default configuration, so I'm hoping this adaptor will change all that. 

{% include figure image_path="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/hasu-usb-usb.jpg" alt="" caption="What a cutie. I should print a case for it, though."%}
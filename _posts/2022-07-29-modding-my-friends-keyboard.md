---
title: Modding a Cheap Keyboard
tags:
    - HIDs
    - Builds
excerpt: "Giving a cheap keyboard a makeover!"
header:
    og_image: /assets/images/posts/2022-07-23-modding-my-friends-keyboard/final-0.jpg
    teaser: /assets/images/posts/2022-07-23-modding-my-friends-keyboard/final-0.jpg
    header: /assets/images/posts/2022-07-23-modding-my-friends-keyboard/final-0.jpg
    overlay_image: /assets/images/posts/2022-07-23-modding-my-friends-keyboard/final-0.jpg
---
Some close friends of mine own a cheap Velocifire TKL61WS mechanical keyboard. Since they first purchased this keyboard, they've gone deep down the mk rabbit hole (of which, I obviously had nothing to do with ...), and no longer feel very impressed with the keyboard. I thought it might be a fun project and gift if I modded it for them. This blog post details my modding adventures. 

## Disassembly

Here's a photo of the original keyboard with some of its default keycaps still in place. Something of a looker, but not necessarily in the best way:

{% include figure image_path="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/original.jpg" alt="" caption="Not the most handsome fellow in the world. It also sounds awful. If I owned a decent mic, I'd try and record the typing sound, just for comparison with an 'after' video ... but perhaps it's a small fortune that I can't share its original sound profile with the world, haha. We're going to try and change all that though. It's makeover time!"%}

We start by unscrewing all the screws on the switch plate, which is what's affixing the plate and the PCB onto the case.

<figure class="half">
    <a href="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/unscrewed.jpg"><img src="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/unscrewed.jpg"></a>
    <a href="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/jst-cable.jpg"><img src="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/jst-cable.jpg"></a>
    <figcaption>Yum, stock Gateron browns :unamused:. There's a 1800 mAh 3.7 V battery though! That's a decent amount of juice. It's connected to the PCB via a 2-pin JST cable. Gotta unplug that sucker.</figcaption>
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

I realized after the switches came in, however, that the PCB accepted only 3-pin switches and not 5-pin switches (the term 'pin' here is kind of silly, because three of the 'pins' are just plastic protrusions that help secure the switch, but everyone in keyboard land just calls them 'pins'). So I had to cut the two plastic legs off each Jwick, so that they effectively became 3-pin switches. The switches still weren't fitting into the PCB though, and I realized that not only were the keyboard's original Gateron Browns 3-pins, but they also possessed a large cavity at the back of the switch, so that the PCB's RGB lights could shine behind each alpha key. The Jwiks did not have such a cavity, however, and so they refused to sit flush against the PCB, while the LEDs were still there. 

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

With the switches and keycaps installed, I tried a few key presses, just to approximate for the typing feel (not so much the typing sound though, because I found that a representative acoustic test requires the keyboard to be mounted to its case). I was pretty happy with all the keys, except for the spacebar. It just felt kind of weak, given the lighter switch, even though the plastic of the keycaps were also pretty light---but I guess the spacebar is just a really big key. I swapped out the switch for a heavier Cherry MX Black. 

{% include figure image_path="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/spacebar-mx-black.jpg" alt="" caption="The right switch for the job."%}

## Undo Mistakes

It turns out that when I was removing the cheap 'hot-swap' switch sockets during the [disassembly](#disassembly) process, I also removed the PCB's copper tracing along certain switch footprints on the PCB. I shouldn't have been too surprised about this wrinkle, given the general quality of the PCB, but I felt like it still could have been avoided. I took me more time than I'd like to admit to figure out the [keyboard matrix circuit](https://en.wikipedia.org/wiki/Keyboard_matrix_circuit) on this PCB, but I got it [eventually](https://www.keyboardtester.com/tester.html), and I used some thin wires to re-establish the lost connections.

{% include figure image_path="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/my-mistakes.jpg" alt="" caption="**My repairs**. I used six pieces of 30 AWG wire to reconnect the traces that I broke off with my somewhat aggressive desoldering."%}

## Remove Ugly Silkscreen Logo

The keyboard's original case has a really ugly logo that loudly reads "Velocifire" on its front. I got rid of it with some nail polish remover (acetone) and a lint-free cloth. The case is made of ABS plastic, so acetone also has a smoothing effect on the case. 

{% include figure image_path="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/acetone-cleaning.jpg" alt="" caption="What the case looks like, while in the middle of acetone cleaning. You can see a faint bit of the logo still left on the front of the case."%}

## Add a Gasket Mount

The way a keyboard is mounted is critical to its typing feel and sound. I think a fantastic and straightforward way of mounting a keyboard's PCB and switch plate to the case is via a soft o-ring gasket. This strategy was made famous by the [Bakeneko 60](https://github.com/kkatano/bakeneko-60), and I've also used it myself for my ['Planckeneko'](https://github.com/hanhanhan-kim/kbd-cases) project. I got the idea of using an o-ring gasket mount as a part of a modding-on-the-cheap project from one of my fave keyboard YouTube channels, [Keybored](https://www.youtube.com/c/Keybored):

{% include video id="zt-WsH7Z9c8" provider="youtube" %}

I think I'm going to take the same approach as the video, and saw off the original plastic standoff mounts, so that they no longer provide any mounting contacts, and all contacts are done via the gasket instead. There are a ton of integrated stand-offs on this keyboard case. I cut off _all_ of them. I used some flush cutters to get rid of the stand-offs. 

{% include figure image_path="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/some-cut-standoffs.jpg" alt="" caption="I started off by snipping just a few of the middle standoffs. The gasket-mount effect just wasn't there though, for as long as the PCB made hard contacts against the plastic . . ."%}

{% include figure image_path="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/all-standoffs-cut.jpg" alt="" caption="In the end, I cut off every plastic standoff. I also wound up cutting the plastic supports on the edges, after I took this photo."%}

In the above Keybored video, the PCB had a daughterboard for the USB port, which is expected of most gasket-mounted keyboards. The logic to having daughterboards is that if the PCB is going to have some pliance for that soft typing feel, you don't want the USB port cut-out on the case to prevent the PCB's vertical flexibility. Without a daughterboard for the USB port, the case's USB cutout would be on the main PCB, and it would be making a hard contact with the USB port, which would inhibit any vertical give. So the favoured solution is to separate the USB port onto a daughterboard. 

Alternatively, if not using a daughterboard, one could create space between the USB port and the USB cutout on the case. Some aesthetic purists might argue that there being such a buffer space between the USB port and the cutout might be a little ugly, but very popular and good-looking boards, such as the recent QK65, [have successfully taken this approach](https://www.youtube.com/watch?v=N3iIDylTRwY)[^1].

{% include figure image_path="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/still-yt-qk65.png" alt="" caption="A still from Keybored's [review video of the QK65](https://www.youtube.com/watch?v=N3iIDylTRwY&t=1235s), where he shows how making the USB cutout larger than the USB port is necessary for a proper gasket-mounted keyboard, if not using a daughterboared."%}

The PCB I'm working with isn't very compatible with a daughterboard, so I opted to go down the QK65 route. I used a dremel to enlarge the USB port. I might have overdone it a bit, but I think it's still fine, overall. 

{% include figure image_path="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/dremel-usb-cutout.jpg" alt="" caption="I enlarge the USB cut-out with a dremel."%}
{% include figure image_path="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/dremelled.jpg" alt="" caption="The finished outcome!"%}

I then ordered the secret sauce: an o-ring gasket. I'm using the [same o-ring gasket](https://www.theoringstore.com/store/index.php?main_page=product_info&products_id=54816) as the one for the original Baknekeko 60. I wrapped the o-ring around the PCB and switch plate, as is standard practice. 

{% include figure image_path="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/o-ring.jpg" alt="" caption="**The recommended o-ring for Bakeneko60 installed on the modded keyboard.** The o-ring was not as stretchy as I thought it'd be. Or at least, it's not nearly as stretchy as the o-ring I used for my [Planckeneko](https://github.com/hanhanhan-kim/kbd-cases/tree/main/planckeneko) project, even though both o-rings are rated at the same hardness. Hmmm."%}

I found that the o-ring was squeezing out some of the sticky tape that I put on the underside of the switch plate. So I removed the sticky tape strips that were on the switch plate edges. 

{% include figure image_path="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/pull-out-sticky-tape.jpg" alt="" caption="Look at me pull out the sticky tape that was on the switch plate edges."%}

## Tape Mod

If not using a semi-flex PCB with lots of flex cutouts, I think it's usually a good idea to do the popular '[tape mod](https://www.youtube.com/watch?v=g7-syoxeIBQ)', and tape the back of the PCB, preferably with the 3M 'blue tape'. I used 3 layers, and I made sure to leave space for the battery power switch and the battery JST socket. 

![](/assets/images/posts/2022-07-23-modding-my-friends-keyboard/tape-mod.jpg)

## Case Foam and Finishing Hardware Touches
I really experimented with what foams to use for the case foam. I had a fair bit of space I got to work with, after I cut off all the excess plastic standoffs. I tried various combinations of [car sound deadener](https://www.amazon.com/car-sound-deadening-material/s?k=car+sound+deadening+material), PE foam, and drawer liner. In the end, I took everything out, except for a single layer of the drawer liner, because that's what I thought sounded best for this board!

{% include figure image_path="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/put-in-keyboard.jpg" alt="" caption="The o-ring gasket worked quite well, and I was able to fit the PCB and switch plate into the keyboard case without a hassle! Ignore the PE foam in this photo, I wound up taking it out, and sticking with only the drawer liner."%}

I was also relieved to see that the toggle switch that controls the battery power (this keyboard is Bluetooth-capable) was still able to jut out of its cut-out without a problem! :tada:

![](/assets/images/posts/2022-07-23-modding-my-friends-keyboard/bottom.jpg)

## Make it QMK-Programmable (a fail :disappointed:)

I own a Hasu USB-USB converter, from back when I first got started in the hobby. I don't use it anymore, because I don't like boards that aren't natively programmable, but I think it might just the thing for this modding project. I recall my friends mentioning how confusing it is to access the arrow keys with the Velocifire's default configuration, so I'm hoping this adaptor will change all that. 

{% include figure image_path="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/hasu-usb-usb.jpg" alt="" caption="What a cutie. I should print a case for it, though."%}

Unfortunately, the hope was misplaced. I knew that [not all keyboards would be compatible](https://geekhack.org/index.php?topic=69169.0) with the Hasu USB-USB controller. The Hasu USB-USB controller worked great with various other boards I own, but failed to work with the Velocifire. I tried to get a closer look at the µC the keyboard uses, just for my own curiousity, but it was really hard to make out. It didn't actually matter anyway. It was just a little disappointing that I couldn't QMK-ify my friends' keyboard :disappointed:. 

{% include figure image_path="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/uc.jpg" alt="" caption="What on earth is this monstrousity?!"%}

## End Result
In the end, I was pretty happy with the result! I thought it looked pretty good, and the typing sound and feel is vastly improved from before. Here are a few photos of the end result! 

![](/assets/images/posts/2022-07-23-modding-my-friends-keyboard/final-0.jpg)

![](/assets/images/posts/2022-07-23-modding-my-friends-keyboard/final-1.jpg)

{% include figure image_path="/assets/images/posts/2022-07-23-modding-my-friends-keyboard/ready.jpg" alt="" caption="Ready to be returned to my buds!"%}

I'm hoping to build a microphone soon, which I'll be able to use to make a decent keyboard typing test. I'll then update this blog post with the recording!

## Footnotes

[^1]: Flip to [4:54](https://www.youtube.com/watch?v=N3iIDylTRwY&t=294s) and [20:35](https://www.youtube.com/watch?v=N3iIDylTRwY&t=1235s) of this Keybored video, to see Scott talk about the lack of daughterboard on the gasket-mounted QK65. 
---
title: Building a Retro Arcade Controller
tags:
    - HIDs
    - Builds
excerpt: ":joystick: Building a retro arcade-style controller, primarily for classic fighting games."
header:
    og_image: /assets/images/posts/2022-09-17-building-a-retro-arcade-controller/21.jpg
    teaser: /assets/images/posts/2022-09-17-building-a-retro-arcade-controller/21.jpg
    header: /assets/images/posts/2022-09-17-building-a-retro-arcade-controller/21.jpg
    overlay_image: /assets/images/posts/2022-09-17-building-a-retro-arcade-controller/21.jpg
---

A good friend of mine is really into fighting games, like [Tekken](https://en.wikipedia.org/wiki/Tekken). Recently, he visited me from France, and told me that in the fighting game subculture, people __always__ play with [arcade controllers](https://en.wikipedia.org/wiki/Arcade_controller) or as they're called by the fandom, "[fight sticks](https://www.reddit.com/r/fightsticks/)". Apparently modern-day controllers, like those seen on an Xbox or a PlayStation, as well as regular keyboards, are shunned by the community. I didn't read up on why fighting game enthusiasts are so pro-fight stick and so anti-non-fight stick, but perhaps there are some real reasons, because fight sticks can hit a sticker price of [$250](https://www.hitboxarcade.com/) :money_mouth_face:. I have no idea how a game controller can be worth multiple hundreds of dollars, because I feel like the basic electronics of a HID are generally quite straightforward. So, I thought I would put my money where my thoughts are, and build one from scratch, and then gift the fight stick to my Tekken-loving French friend. I then actually wound up building another fight stick (a slightly different variant) for myself, so I could use it while playing with him. I also have a weakness for HIDs (which is pretty clear from this blog), so why not add another one to the collection :joy:. 

## The "Slimbox"
I have a bunch of leftover Kailh low-profile choc v1 switches, from the many keyboards I've built. I found some [`.stl`s on Thingiverse](https://www.thingiverse.com/thing:4880590) for a fight stick enclosure that's built around low profile Kailh switches. The designer named it the "Slimbox". The Thingiverse project also includes `.stl`s of circular keycaps for the Kailh switches, in order to complete the vintage arcade-style look. I printed the enclosure and the keycaps in PETG, and I popped some switches into the printed enclosure. I used Kailh silvers for the movement buttons (linear, 40 g) and Kailh browns for the action and menu buttons (tactile, 60 g). 

{% include figure image_path="/assets/images/posts/2022-09-17-building-a-retro-arcade-controller/0.jpg" caption="The printed enclosure with the Kailh low-profile switches popped in."%}

I then tried to press in the circular keycaps onto the switches, but the stems of the printed keycaps were too thick. I found that I had to file down the stems for all the keycaps. 

<figure class="half">
    <a href="/assets/images/posts//2022-09-17-building-a-retro-arcade-controller/1.jpg"><img src="/assets/images/posts//2022-09-17-building-a-retro-arcade-controller/1.jpg"></a>
    <a href="/assets/images/posts/2022-09-17-building-a-retro-arcade-controller/2.jpg"><img src="/assets/images/posts/2022-09-17-building-a-retro-arcade-controller/2.jpg"></a>
    <figcaption>I file down the stems of the circular keycaps, so that they'd press-fit into the sockets of the Kailh switches. Otherwise, I found that the keycaps would not fit.</figcaption>
</figure>

I noticed that the switches were not fitting super snugly in place, into the enclosure. This was not unexpected, given that PETG does not print bridges and overhangs nearly as well as PLA, and the part of the enclosure that's socketed for the switches is comprised entirely of bridges and overhangs. To rectify the loose fitting, I used hot glue to secure the switches into place. 

{% include figure image_path="/assets/images/posts/2022-09-17-building-a-retro-arcade-controller/3.jpg" caption="Nothing some hot glue can't fix."%}

After much filing of keycap stems, I finally managed to pop all the keycaps into the switches, except for the dedicated smaller keycaps meant for the "start" and "select" buttons. I noticed that these keycaps printed a little too wide, and so they wouldn't fit into the enclosure's cavity. I also found their surface to be a little too flimsy. To address these problems, I adjusted in Prusa Slicer, the x and y scaling to 98%, and the z scaling to 200%. Doubling the z scaling resulted in some very tall keycap stems, and so I just clipped those to size with a pair of flush cutters. 

<figure class="half">
    <a href="/assets/images/posts//2022-09-17-building-a-retro-arcade-controller/4.jpg"><img src="/assets/images/posts//2022-09-17-building-a-retro-arcade-controller/4.jpg"></a>
    <a href="/assets/images/posts/2022-09-17-building-a-retro-arcade-controller/5.jpg"><img src="/assets/images/posts/2022-09-17-building-a-retro-arcade-controller/5.jpg"></a>
    <figcaption>The keycaps for the "start" and "select" buttons weren't sized quite right, but with some resizings in the slicer, everything turned out just fine!</figcaption>
</figure>

With the keycaps secured into the switches, and the switches secured into the enclosure, I tried pressing the Slimbox's buttons a few times, just to see how the buttons felt and sounded. They feel very nice and they sound very nice. 

{% include video id="iTG-WGE2DBw" provider="youtube" %}

I then wired the electronics up. The hook ups for momentary switch-based HIDs are generally quite simple, One lead of the switch goes into the common GND of the µC, and the other lead of each switch goes to a dedicated digital pin on the µC. I use a cheap Arduino Pro Micro clone as my µC. 

{% include figure image_path="/assets/images/posts/2022-09-17-building-a-retro-arcade-controller/6.jpg" caption="The internal wiring is very straightforward: each switch has one lead going into a dedicated pin on the µC, and the other lead going into a common GND."%} 

The [firmware](https://github.com/jfedor2/gamepad) for button-only game controllers is pretty straightforward. Notably, the firmware doesn't trick the host PC into thinking that it's a keyboard. Rather it tells the PC that it's an actual game controller. I had to adjust the code a little bit, just so that the pin-function mappings on [lines 9-22](https://github.com/jfedor2/gamepad/blob/master/Gamepad/Gamepad.ino#L9-L22) match the µC pins that I hooked up each button to. The Arduino pin numbers for the Arduino Pro Micro can be found [here](https://cdn.sparkfun.com/assets/9/c/3/c/4/523a1765757b7f5c6e8b4567.png), and are highlighted in blue. So, for example, the silkscreened "A3" pin on the Pro Micro PCB should be defined as `21` in the firmware. So if the button that you want to program as "up" is connected to "A3" on the Pro Micro, you should change line 9 in the firmware, so that instead of pin `2`, it's pin `21`. 

After mapping the button functions in the firmware, I plugged in a USB cable, and connected the controller to a computer, to see if everything would work properly! And it does!

{% include video id="8m3KYTJUaNg" provider="youtube" %}

{% include figure image_path="/assets/images/posts/2022-09-17-building-a-retro-arcade-controller/9.jpg" caption="I'm happy with the result! A good gift for a good friend."%}

## The "Hitbox"
I had so much fun building my friend's "Slimbox" fight stick, that I decided to build my own. I opted for a slightly different version, however, that doesn't use mechanical keyboard switches. Rather it uses classic round arcade-style buttons, and is dubbed a "Hitbox"-style controller (presumably because it has the same layout as this [super expensive fight stick called a Hitbox](https://www.hitboxarcade.com/)). I printed the enclosure from some [Thingiverse `.stl`s](https://www.thingiverse.com/thing:4888965) in grey PETG. 

{% include figure image_path="/assets/images/posts/2022-09-17-building-a-retro-arcade-controller/11.jpg" caption="The colour reminded me of a North American Super Nintendo system."%}

The grey PETG gave me some strong [Super Nintendo](https://en.wikipedia.org/wiki/Super_Nintendo_Entertainment_System) vibes, so I thought maybe I could build my Hitbox with a similar colour scheme. I decided to order some grey, purple, and black Sanwa brand buttons from [Acade Shock](https://arcadeshock.com/). Supposedly, Sanwa buttons are the best in the business, but I am just parroting the internet---I know nothing about this subculture :man_shrugging:. 

{% include figure image_path="/assets/images/posts/2022-09-17-building-a-retro-arcade-controller/10.jpg" caption="Some extra crispy buttons! They came in just 2 days' time."%}

I then pushed the buttons into the enclosure cut-outs, and they snapped into place in a very satisfying manner. 

<figure class="half">
    <a href="/assets/images/posts/2022-09-17-building-a-retro-arcade-controller/15.jpg"><img src="/assets/images/posts/2022-09-17-building-a-retro-arcade-controller/15.jpg"></a>
    <a href="/assets/images/posts/2022-09-17-building-a-retro-arcade-controller/12.jpg"><img src="/assets/images/posts/2022-09-17-building-a-retro-arcade-controller/12.jpg"></a>
    <figcaption>Looks good with the buttons popped into the enclosure! The purple colour is not nearly as dark as I'd want them to be, but everything still looks good, I think</figcaption>
</figure>

I then moved onto the electronics hook-up. The hook-up for the Hitbox is identical to the Slimbox: a common GND wire and a wire that maps a single button to a single pin on the µC. 

<figure class="half">
    <a href="/assets/images/posts//2022-09-17-building-a-retro-arcade-controller/14.jpg"><img src="/assets/images/posts//2022-09-17-building-a-retro-arcade-controller/14.jpg"></a>
    <a href="/assets/images/posts/2022-09-17-building-a-retro-arcade-controller/17.jpg"><img src="/assets/images/posts/2022-09-17-building-a-retro-arcade-controller/17.jpg"></a>
    <figcaption>Some of the cleanest wiring I've ever done. I am proud.</figcaption>
</figure>

I use the exact same firmware for the Hitbox that I used with the Slimbox. Again, I adjust the pin-function mappings on [lines 9-22](https://github.com/jfedor2/gamepad/blob/master/Gamepad/Gamepad.ino#L9-L22), just like I did with the Slimbox. 

I then sealed up the enclosure. Just like with the Slimbox, there's a backplate that screws into the bottom of the main enclosure. The problem though is that the enclosure screw holes are a little too small. So I just took a drill to each printed screw hole to widen the holes. I then tapped the holes with 4-40 threads. 

<figure class="half">
    <a href="/assets/images/posts//2022-09-17-building-a-retro-arcade-controller/18.jpg"><img src="/assets/images/posts//2022-09-17-building-a-retro-arcade-controller/18.jpg"></a>
    <a href="/assets/images/posts/2022-09-17-building-a-retro-arcade-controller/19.jpg"><img src="/assets/images/posts/2022-09-17-building-a-retro-arcade-controller/19.jpg"></a>
    <figcaption>After drilling out the printed screw holes, the holes became wide enough that I could tap some 4-40 threads into them. The back plate could then seal into the enclosure without a problem.</figcaption>
</figure>

The Hitbox works great! These Sanwa buttons provide a lovely retro arcade feel. 

{% include video id="4DovGtMwdO0" provider="youtube" %}

I enjoy the colour scheme of the finished product as well. It doesn't exactly match the Super Nintendo vibe I was going for, but I think it's a reasonable approximation! In either case, I like it! :grinning:

![](/assets/images/posts//2022-09-17-building-a-retro-arcade-controller/super_nintendo.jpg)

![](/assets/images/posts//2022-09-17-building-a-retro-arcade-controller/21.jpg)

![](/assets/images/posts//2022-09-17-building-a-retro-arcade-controller/22.jpg)
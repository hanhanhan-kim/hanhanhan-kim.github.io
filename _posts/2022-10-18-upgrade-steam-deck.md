---
title: Upgrading my Steam Deck
header:
    header: /assets/images/posts/2022-11-08-upgrading-my-steam-deck/4.jpg
    teaser: /assets/images/posts/2022-11-08-upgrading-my-steam-deck/4.jpg
    og_image: /assets/images/posts/2022-11-08-upgrading-my-steam-deck/4.jpg
    overlay_image: /assets/images/posts/2022-11-08-upgrading-my-steam-deck/4.jpg
excerpt: ":steam_locomotive: Upgrade the Steam Deck gaming console!"
tags: 
    - Computers
---

I'm very much enjoying my Steam Deck. Even though I don't really play many single player video games anymore[^1], I find that the Steam Deck is a great system for some casual gaming from the comforts of my bed or armchair. 

One of the coolest things about the Steam Deck is how repairable and upgradable it is. In fact, Valve officially partnered with iFixit, and as a result, the iFixit website provides [incredibly clear guides](https://www.ifixit.com/Device/Steam_Deck) for repairing the Steam Deck, and is also an official authorized seller for Steam Deck replacement parts. In this blog post, I detail my various upgrades and hacks I perform on my Steam Deck. 

## Replacing the SSD

I bought the cheapest Steam Deck, which comes with 64 GB of storage in a 2230 M.2 form factor. I knew, however, that I was going to replace the storage before I even ordered my deck because 64 GB isn't much memory, and I saw a good deal for a 512 GB SKHynix SSD in a 2230 form factor [for about $100 bucks](https://www.amazon.com/gp/product/B0B8Q9HJKQ/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1).

Replacing the SSD is quite straightforward, especially with [this crystal-clear official guide](https://www.ifixit.com/Guide/Steam+Deck+SSD+Replacement/148989). Everything can be done with my very trusty---albeit pricey---[iFixit Pro Tech Toolkit](https://www.ifixit.com/Store/Tools/Pro-Tech-Toolkit/IF145-307), which I use for pretty much any kind of electronics project. We begin, not surprisingly, by opening up the deck. We need only a pry tool to open up the deck.

<figure class="half">
    <a href="/assets/images/posts/2022-11-08-upgrading-my-steam-deck/0.jpg"><img src="/assets/images/posts/2022-11-08-upgrading-my-steam-deck/0.jpg"></a>
    <a href="/assets/images/posts/2022-11-08-upgrading-my-steam-deck/1.jpg"><img src="/assets/images/posts/2022-11-08-upgrading-my-steam-deck/1.jpg"></a>
</figure>

We carefully peel up a bit of aluminium tape with a pair of angled tweezers. Doing so will reveal a screw, which we unscrew.

![](/assets/images/posts/2022-11-08-upgrading-my-steam-deck/2.jpg)

We unscrew some tiny screws found on the bottom and the top left corners, which are marked in red, in the below image. 

![](/assets/images/posts/2022-11-08-upgrading-my-steam-deck/3.jpg)

We then lift off the cover piece that was secured by the three screws. Doing so will reveal the SSD drive. Before we doing anything with the SSD, however, we should disconnect the battery jumper:

<figure class="half">
    <a href="/assets/images/posts/2022-11-08-upgrading-my-steam-deck/4.jpg"><img src="/assets/images/posts/2022-11-08-upgrading-my-steam-deck/4.jpg"></a>
    <a href="/assets/images/posts/2022-11-08-upgrading-my-steam-deck/5.jpg"><img src="/assets/images/posts/2022-11-08-upgrading-my-steam-deck/5.jpg"></a>
</figure>

We can now move onto swapping out the SSD. The SSD slot is located on the bottom, and the SSD itself is secured via a screw, which we unscrew. We then pull out the SSD, and gently slip off the foil cover that is blanketing the the SSD. Here's a comparison of the stock Steam Deck 64 GB SSD and my new 512 GB SSD:

<figure class="half">
    <a href="/assets/images/posts/2022-11-08-upgrading-my-steam-deck/6.jpg"><img src="/assets/images/posts/2022-11-08-upgrading-my-steam-deck/6.jpg"></a>
    <a href="/assets/images/posts/2022-11-08-upgrading-my-steam-deck/7.jpg"><img src="/assets/images/posts/2022-11-08-upgrading-my-steam-deck/7.jpg"></a>
</figure>

We plug in the new 512 GB SSD.

<figure class="half">
    <a href="/assets/images/posts/2022-11-08-upgrading-my-steam-deck/8.jpg"><img src="/assets/images/posts/2022-11-08-upgrading-my-steam-deck/8.jpg"></a>
    <a href="/assets/images/posts/2022-11-08-upgrading-my-steam-deck/9.jpg"><img src="/assets/images/posts/2022-11-08-upgrading-my-steam-deck/9.jpg"></a>
</figure>

Normally, at this point, we'd start reassembling the Steam Deck. Except we're actually now going to start preparing the Steam Deck software while the Deck's guts are still exposed, in case we need to fiddle around with some additional hardware troubleshooting (e.g. maybe the new drive is dead on arrival, who knows). Given that the new SSD is brand spanking new, it doesn't have any software yet, including Steam OS. To get Steam OS on our machine, we first make a bootable USB drive that has the official Steam OS image. We start by [downloading the OS from the Steam website](https://store.steampowered.com/steamos/download/?ver=steamdeck&snr=), and we then flash the OS onto a USB drive, via a software like [Balena Etcher](https://www.balena.io/etcher/). Once the OS is flashed onto the USB drive, we insert the drive into the Steam Deck. 

![](/assets/images/posts/2022-11-08-upgrading-my-steam-deck/10.jpg)

We then hold down the Volume (-) and power buttons until a tone plays. The Steam Deck boot logo will then pop up on the Deck scren, followed by the boot manager. We select the USB drive as the device from which to boot. 

<figure class="half">
    <a href="/assets/images/posts/2022-11-08-upgrading-my-steam-deck/11.jpg"><img src="/assets/images/posts/2022-11-08-upgrading-my-steam-deck/11.jpg"></a>
    <a href="/assets/images/posts/2022-11-08-upgrading-my-steam-deck/12.jpg"><img src="/assets/images/posts/2022-11-08-upgrading-my-steam-deck/12.jpg"></a>
</figure>

A prompt with four options will then appear. Of these options, we select "Re-image Steam Deck", and then "Confirm". The Steam Deck will then hum and haw for a little while, and then the Steam Deck will reboot. Upon this reboot, the Deck should act like a freshly bought store-bought device! 

<figure class="half">
    <a href="/assets/images/posts/2022-11-08-upgrading-my-steam-deck/13.jpg"><img src="/assets/images/posts/2022-11-08-upgrading-my-steam-deck/13.jpg"></a>
    <a href="/assets/images/posts/2022-11-08-upgrading-my-steam-deck/14.jpg"><img src="/assets/images/posts/2022-11-08-upgrading-my-steam-deck/14.jpg"></a>
    <figcaption>The Deck goes into desktop mode for a bit, after we select "Confirm", and we can see the terminal outputs. The Deck then restarts and reveals a first time start-up menu, just like a freshly bought stock Steam Deck!</figcaption>
</figure>

We navigate into the storage part of the settings and check that the storage capacity is about 512 GB. 

![](/assets/images/posts/2022-11-08-upgrading-my-steam-deck/16.jpg)

Hooray, looks great!

## Replacing the Joysticks

I also wanted to replace the joysticks with some fancy [Hall effect-based joysticks from Gulikit](https://www.amazon.com/gp/product/B0B8MH58WS/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1). I have the Gulikit King Kong 2 Pro controller, and its joysticks' precision and lack of drift provides me with a lot of peace of mind[^2]. So I wanted to implement Hall effect-based joysticks on my Steam Deck as well. 

The issue, however, is that the Steam Deck's joysticks can be either "Type A" or "Type B", and the Gulikit's Hall effect-based joysticks **only fully support Type A** as of 2022/12/03---more specifically, [the capacitive touch sensing function won't work, if the Steam Deck isn't built as Type A](https://www.reddit.com/r/SteamDeck/comments/xyyth7/gulikit_mhda_type_b/). My Steam Deck appears to be Type B:

<figure>
    <a href="/assets/images/posts/2022-11-08-upgrading-my-steam-deck/15.jpg"><img src="/assets/images/posts/2022-11-08-upgrading-my-steam-deck/15.jpg"></a>
    <figcaption>The underlined yellow part reads "MHDA", which means that the Deck is using Type A controllers, as explained <a href="https://twitter.com/GuliKitDesign/status/1580797077306544129">here</a>.</figcaption>
</figure>


I could swap out the joysticks anyway, and enjoy the Hall effect-based joysticks, but I'd rather my Deck be completely functional. So I'm going to wait until Gulikit builds Type B Hall effect-based joysticks for the Steam Deck. I'll update this post then. 

## Footnotes
[^1]: I find that multiplayer games are a fun way to catch up with friends. They also do a good job filling in otherwise awkward silences during conversation. 
[^2]: Back when I owned a Nintendo Switch, I was one of the many victims of the Switch's notorious joystick drift. Ever since then, I've been paranoid of joysticks drifting on me. Hall effect-based joysticks don't use mechanical contacts typical of potentiometers, and instead use electromagnetic (EM) fields. The lack of physical contact in EM-based joysticks means that there isn't as much wear and tear from frequent use. 
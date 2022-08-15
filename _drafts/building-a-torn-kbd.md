---
title: Building a Torn Keyboard
excerpt: ":busts_in_silhouette:	 Yet another keyboard build! This one has two rotary encoders and an OLED screen!"
tags:
    - HIDs
    - Builds
# header:
#     og_image: /assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/16.jpg
#     teaser: /assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/16.jpg
#     header: /assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/16.jpg
#     overlay_image: /assets/images/posts/2022-08-08-building-a-wireless-ffkb-kbd/16.jpg  
---

In this post, I build the [Torn](https://github.com/rtitmuss/torn) keyboard! Like all my keyboards, it's a 40%, and it's also a wired split. It also sports some fun features that my other keyboards don't have. Namely, it has two (and can support up to 6!) rotary encoders, as well as an OLED screen.

## Electronics

The Torn's PCBs are not reversible. In some ways, I kind of like that. You can more easily cram a bunch of features in, such as supporting different switch and socket types. 

{% include figure image_path="/assets/images/posts/2022-08-14-building-a-torn-kbd/bare-pcb.jpg" caption="The bare PCBs."%}

The keyboard uses some fairly standard keyboard electronics parts. In general, the documentation for the Torn is insanely good. I just followed the [PCB assembly guide](https://github.com/rtitmuss/torn/blob/master/doc/pcb.md), exactly. The result was a fine looking keyboard. 

{% include figure image_path="/assets/images/posts/2022-08-14-building-a-torn-kbd/soldered.jpg" caption="The populated PCBs"%}

## Case

The designer of the Torn also made a few case options. One of the really intriguing designs was the [tented 'wedge' case](https://github.com/rtitmuss/torn/blob/master/case/wedge/wedge.md). This design is not open-sourced, however, and I needed to ask the designer, [Richard Titmuss](https://github.com/rtitmuss), for the files. I messaged him on Discord (I found him via the very helpful [Torn Discord server](https://discordapp.com/users/745293992044003348/)), and for a very modest price, he shared with me a 20 tented version of the wedge case. I printed the case in black PETG, and even though the documentation suggests M3 inserts, I found that M2 inserts fit the case's insert holes a little easier (M2 screws also still have large enough heads that they can secure all the parts in place.)

<figure class="third">
    <a href="/assets/images/posts/2022-08-14-building-a-torn-kbd/case.jpg"><img src="/assets/images/posts/2022-08-14-building-a-torn-kbd/case.jpg"></a>
    <a href="/assets/images/posts/2022-08-14-building-a-torn-kbd/case-w-threads.jpg"><img src="/assets/images/posts/2022-08-14-building-a-torn-kbd/case-w-threads.jpg"></a>
    <a href="/assets/images/posts/2022-08-14-building-a-torn-kbd/case-w-inserted-threads.jpg"><img src="/assets/images/posts/2022-08-14-building-a-torn-kbd/case-w-inserted-threads.jpg"></a>
    <figcaption>I printed the base of the case in PETG, and then used a soldering iron to push in the M2 brass inserts.</figcaption>
</figure>

I then did what the docs suggested, and put in some adhesive weights that are meant to balance car wheels. They're pretty cheap, and honestly, I should have bought more, to add even more weight to the case. 

<figure class="half">
    <a href="/assets/images/posts/2022-08-14-building-a-torn-kbd/case-w-weights.jpg"><img src="/assets/images/posts/2022-08-14-building-a-torn-kbd/case-w-weights.jpg"></a>
    <a href="/assets/images/posts/2022-08-14-building-a-torn-kbd/case-w-weights-inside.jpg"><img src="/assets/images/posts/2022-08-14-building-a-torn-kbd/case-w-weights-inside.jpg"></a>
    <figcaption>I had enough room to double the number of weights, but I didn't buy enough. No matter, I'll just add other stuff in, instead.</figcaption>
</figure>

I had plenty of room, so I thought I'd do something a little unconventional, and add towels! Well, they're actually [Amazon's microfibre cleaning cloths](https://www.amazon.com/gp/product/B009FUF6DM/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1), but historically, I find towels to be the best sound dampeners of all time. If you just fold a towel a few times and put that under your keyboard as a deskmat, you get insanely improved sounds. So I thought, why not do that inside a keyboard, given that this case has so much room to work with? I cut a cleaning cloth in two, folded the pieces up, and put them in the case. 

![](/assets/images/posts/2022-08-14-building-a-torn-kbd/case-w-towels.jpg)


## Finishing Touches

## Future Improvements
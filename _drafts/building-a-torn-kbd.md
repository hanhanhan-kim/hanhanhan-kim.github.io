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

### 7-deg Wedge Case

The designer of the Torn also made a few case options. One of the really intriguing designs was the [tented 'wedge' case](https://github.com/rtitmuss/torn/blob/master/case/wedge/wedge.md). This design is not open-sourced, however, and I needed to ask the designer, [Richard Titmuss](https://github.com/rtitmuss), for the files. I messaged him on Discord (I found him via the very helpful [Torn Discord server](https://discordapp.com/users/745293992044003348/)), and for a very modest price, he shared with me a 7 degree tented version of the wedge case (for the price, he also shipped to me a pair of steel switch plates, which arrived in the US after a month or so). I printed the case in black PETG. 

TODO: FIGS

I then did what the docs suggested, and put in some adhesive weights that are meant to balance car wheels. They're pretty cheap, and honestly, I should have bought more, to add even more weight to the case. 

<figure class="half">
    <a href="/assets/images/posts/2022-08-14-building-a-torn-kbd/case-w-weights.jpg"><img src="/assets/images/posts/2022-08-14-building-a-torn-kbd/case-w-weights.jpg"></a>
    <a href="/assets/images/posts/2022-08-14-building-a-torn-kbd/case-w-weights-inside.jpg"><img src="/assets/images/posts/2022-08-14-building-a-torn-kbd/case-w-weights-inside.jpg"></a>
    <figcaption>TODO</figcaption>
</figure>


### Hi Pro Case




## Finishing Touches

## Future Improvements
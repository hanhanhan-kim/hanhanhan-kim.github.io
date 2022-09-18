---
title: Building a Torn Keyboard
excerpt: ":busts_in_silhouette:	 Yet another keyboard build! This one has two rotary encoders and an OLED screen!"
tags:
    - HIDs
    - Builds
header:
    og_image: /assets/images/posts/2022-09-18-building-a-torn-kbd/9.jpg
    teaser: /assets/images/posts/2022-09-18-building-a-torn-kbd/9.jpg
    header: /assets/images/posts/2022-09-18-building-a-torn-kbd/9.jpg
    overlay_image: /assets/images/posts/2022-09-18-building-a-torn-kbd/9.jpg 
---

In this post, I build the [Torn](https://github.com/rtitmuss/torn) keyboard! Like all my keyboards, it's a 40%, and it's also a wired split. It also sports some fun features that my other keyboards don't have. Namely, it has two rotary encoders, as well as an OLED screen.

The Torn's PCBs are not reversible. In some ways, I kind of like that. You can more easily cram a bunch of features in, such as supporting different switch and socket types. 

{% include figure image_path="/assets/images/posts/2022-09-18-building-a-torn-kbd/bare-pcb.jpg" caption="The bare PCBs."%}

The keyboard uses some fairly standard keyboard electronics parts. In general, the documentation for the Torn is insanely good. I just followed the [PCB assembly guide](https://github.com/rtitmuss/torn/blob/master/doc/pcb.md), exactly. The result is a fine looking keyboard. 

{% include figure image_path="/assets/images/posts/2022-09-18-building-a-torn-kbd/soldered.jpg" caption="The populated PCBs"%}

The designer of the Torn also made a few case options. One of the really intriguing designs was the [tented 'wedge' case](https://github.com/rtitmuss/torn/blob/master/case/wedge/wedge.md). This design is not open-sourced, however, and I needed to ask the designer, [Richard Titmuss](https://github.com/rtitmuss), for the files. I messaged him on Discord (I found him via the very helpful [Torn Discord server](https://discordapp.com/users/745293992044003348/)), and for a very modest price, he shared with me a `.stl` of a 7 degree tented version of the wedge case (for the price, he also shipped to me a pair of steel switch plates and acrylic covers). I printed the case in black PETG. 

The case has two printed components that layer onto each other: the "trim", which sits on top, and the "base", which sits on the bottom. I started by preparing the trim. I used a soldering iron to install some M3 threaded brass inserts into the three lower holes of the trim pieces (even though, in the end, I opted not to screw anything into these threads).

{% include figure image_path="/assets/images/posts/2022-09-18-building-a-torn-kbd/1.jpg" caption="Install M3 threaded brass inserts in the lower holes only, like so."%} 

I then installed three M3 threaded brass insets into the three top upper holes of the base pieces. I placed the PCBs onto the base. 

{% include figure image_path="/assets/images/posts/2022-09-18-building-a-torn-kbd/2.jpg" caption="If you look carefully, you'll see that some resistors on the left PCB are missing. I forgot to solder them when I took this photo, and the next few photos."%} 

I then installed my switches into the switchplate and PCB. My PCBs have Kailh hotswap sockets, so my switches had to be press-fit into place. For this step, I found it easiest to remove the PCBs from the case, so that I would avoid bending the switchplate as I pressed the switches into the PCBs. 

{% include figure image_path="/assets/images/posts/2022-09-18-building-a-torn-kbd/3.jpg" caption="In these photos, I'm using [Bolsa Techno Violet switches](https://bolsakeyboardsupply.com/products/techno-violet-switches), but I later swap them out for some silent linears."%}

At this point, I uploaded the bootloader. For detailed instructions, see [my blog post](/uploading-kbd-bootloaders) about uploading keyboard bootloaders.   

I then placed the trim on top of the switchplate. Before moving on, however, I had a change of heart and opted for silent [Boba Gum switches (68 g)](https://ringerkeys.com/products/gazzew-bobagums-silent-linear-switches?variant=39438313914450), because I want to use this keyboard at work without being super disturbing. I threw on some [black NPT blank keycaps](https://divinikey.com/products/np-pbt-blank-white-keycap-set). 

<figure class="third">
  <a href="/assets/images/posts/2022-09-18-building-a-torn-kbd/4.jpg">
  <img src="/assets/images/posts/2022-09-18-building-a-torn-kbd/4.jpg"></a>

  <a href="/assets/images/posts/2022-09-18-building-a-torn-kbd/5.jpg">
  <img src="/assets/images/posts/2022-09-18-building-a-torn-kbd/5.jpg"></a>

  <a href="/assets/images/posts/2022-09-18-building-a-torn-kbd/6.jpg">
  <img src="/assets/images/posts/2022-09-18-building-a-torn-kbd/6.jpg"></a>

  <figcaption>Oh look, I still didn't solder on those resistors on the left keyboard half.</figcaption>
</figure>

I wasn't very concerned with the keyboard's sound profile, because I was using silent switches. Still, I decided to do the [tape mod](https://www.youtube.com/watch?v=g7-syoxeIBQ), and I put on three layers of 3M blue tape on the underside of the PCBs. I also added a thin layer of drawer liner inside the base of the case. 

<figure class="half">
  <a href="/assets/images/posts/2022-09-18-building-a-torn-kbd/7.jpg">
  <img src="/assets/images/posts/2022-09-18-building-a-torn-kbd/7.jpg"></a>

  <a href="/assets/images/posts/2022-09-18-building-a-torn-kbd/8.jpg">
  <img src="/assets/images/posts/2022-09-18-building-a-torn-kbd/8.jpg"></a>

  <figcaption>Some keyboard sound profile mods.</figcaption>
</figure>

Finally, I added the acrylic cover and secured all the pieces together with some M3 x 10 mm screws. My rotary encoders spring back into a home position, so I also installed some aggressively tabbed ["chicken head" encoder knobs](https://www.amazon.com/gp/product/B09YNH6MTF/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1). I think the final result is quite nice! 

![](/assets/images/posts/2022-09-18-building-a-torn-kbd/9.jpg)

I brought the keyboard into the office, and I paired the board with some [Fellowes wrist rests](https://www.amazon.com/dp/B000YBZZU0/ref=twister_B08YN7S1FM?_encoding=UTF8&psc=1), to complete the office ergonomics look. The keyboard is both super comfortable and super silent :grinning:. 

![](/assets/images/posts/2022-09-18-building-a-torn-kbd/10.jpg)
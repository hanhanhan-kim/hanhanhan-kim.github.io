---
title: Building a Slim OLKB for My Laptop
tags: 
    - HIDs
    - Builds
excerpt: "A 40% low-profile ortholinear keyboard that sits on top of my laptop's keyboard. Features a custom DIY cable."
---

The only times I regularly use a traditional staggered keyboard is when I'm on my laptop, a Macbook Pro. I like my laptop, but I wish I could use a different keyboard---namely, an ortholinear 40% keyboard. With the exception of some creative solutions, like the [ThinKeys project](https://github.com/moduloindustries/thinkeys) (which is only compatible for certain Lenovo laptops), I'm limited to using an external keyboard. I figured I could still do my best though, and make lugging around an external keyboard a pleasant experience. 

I wanted to be able to place my keyboard on top of my laptop's keyboard without much fiddliness. For this reason, I ruled out a traditional split keyboard, because using a split often requires the user to space the two keyboard halves at shoulder's width apart---so the two halves would be flanking the laptop, during ergonomic use. I could have used a 'split' monoblock keyboard, where the two keyboard halves have a large space between them, but are still integrated onto a single case. The most famous example of such a design is the [Alice](https://geekhack.org/index.php?topic=95054.950)-style keyboard (the original has since inspired many similarly styled keyboards). As much as I like split monoblock boards, I felt that they tend to be larger than they need to be, because of the spacing between the two 'halves'. I wanted to maximize on portability. In addition, I wanted my thumbs to be close to the laptop's trackpad, and the superior ergonomics of a split monoblock keyboard discourages such a position. So, I opted with a 4 x 12 ortholinear grid layout keyboard, which is a layout that I'm very familiar with. 

To make the keyboard as light as possible, I opted for low-profile Kailh Choc switches, instead of traditional Cherry-style switches. These switches use a different footprint from Cherry-style switches, and are also much shorter than their Cherry counterparts. The upside about Choc switches is that they also tend to sound good, even if the keyboard isn't foamed up and gasket-mounted. You can still lube and 'film' the switches though---the 'filming' in this case is referred to as the '[tape mod](https://www.reddit.com/r/ErgoMechKeyboards/comments/qxrtze/choc_lube_tape_modding_guide/)', and it requires the user to insert thin pieces of tape beside the switch stem, to limit stem wobble. In other words, despite having a very different execution, the tape mod has the exact same function that filming does for Cherry-style switches. 

I debated about whether I wanted the keyboard to be wireless. The portable quality of a wireless keyboard is definitely alluring, but given that I wanted this keyboard to sit directly on top of my laptop's keys, as a means of both functionally and physically substituting the default keyboard, I concluded that wireless functionality might be unnecessary. The keyboard was going to be so close to the laptop's USB-C ports, that a cable---provided that I make it a short custom length---was not going to be a nuissance. Besides, I think I want to have some kind of backlighting or per-key lighting, so I can see my keys even in the dark, just like I would with my laptop's default keyboard[^1]. 

The keyboard that seemed to best fit my requirements is the Boardsource [Technik](https://boardsource.xyz/store/5ffb9b01edd0447f8023fdb2). It's a 4 x 12 ortholinear grid keyboard that supports Choc switches. It's USB-C, and it comes with RGB per-key lighting. I don't love RGB, so I'd probably just make those keys glow white. It can come with either an aluminium or polycarbonate case. The latter is cheaper and better for me, because I want to carry this keyboard around, and polycarbonate is far lighter than aluminium. 

{% include figure image_path="/assets/images/posts/2022-07-31-building-a-slim-olkb-for-my-laptop/stock.png" alt="" caption="A photo of the ortholinear Technik from the [Boardsource website](https://boardsource.xyz/store/5ffb9b01edd0447f8023fdb2)." %}

## Building the Keyboard

This keyboard build is super straightforward. The build process is pretty similar to the [Planck](https://olkb.com/collections/planck)'s. The kit comes with the PCB, the case, a FR4 switch plate, some standoffs, and some screws that secure the PCB into the case from the front, and from the back. We first secure the standoffs into the case with the countersunk screws. Then, we align the PCB onto the top of the standoffs. Then, we screw the switch plate onto the stand offs with the button head screws. Finally, we pop in our switches, and top the switches off with some keycaps. I'm using Kailh Low Pro Silver Choc switches (linear, 40 g), that I've [lubed with Krytox 205g0. tape modded, and o-ring modded](https://www.youtube.com/watch?v=3YBNRXRXG0w). I use [light 1/8" orthodontic o-rings](https://www.amazon.com/dp/B00OV1LXG4/ref=cm_sw_r_cp_apa_glc_fabc_WX5JM8M5YEGVVNR2XJG6), so I can minimize travel distance reduction. For my keycaps, I'm using the popular [MBK choc profiles](https://mkultra.click/mbk-choc-keycaps), although I'm hoping I can eventually swap those out for some legended [work.louder](https://worklouder.cc/keycaps/) keycaps. 

<figure class="half">
  <a href="/assets/images/posts/2022-07-31-building-a-slim-olkb-for-my-laptop/technik-parts.jpg">
  <img src="/assets/images/posts/2022-07-31-building-a-slim-olkb-for-my-laptop/technik-parts.jpg"></a>

  <a href="/assets/images/posts/2022-07-31-building-a-slim-olkb-for-my-laptop/technik-standoffs.jpg">
  <img src="/assets/images/posts/2022-07-31-building-a-slim-olkb-for-my-laptop/technik-standoffs.jpg"></a>

  <a href="/assets/images/posts/2022-07-31-building-a-slim-olkb-for-my-laptop/technik-switchplate.jpg">
  <img src="/assets/images/posts/2022-07-31-building-a-slim-olkb-for-my-laptop/technik-switchplate.jpg"></a>

  <a href="/assets/images/posts/2022-07-31-building-a-slim-olkb-for-my-laptop/technik-keycaps.jpg">
  <img src="/assets/images/posts/2022-07-31-building-a-slim-olkb-for-my-laptop/technik-keycaps.jpg"></a>

  <figcaption>Building the Technik keyboard.</figcaption>
</figure>

The keyboard looks pretty spiffy, in the end!

![](/assets/images/posts/2022-07-31-building-a-slim-olkb-for-my-laptop/technik.jpg)

## Making a Custom Length Cable
TODO

## Using Karabiner
The weight of an external keyboard placed on top of a laptop's keyboard will cause the laptop to output undesirable key presses. Fortunately, an open-sourced software called [Karabiner Elements](https://karabiner-elements.pqrs.org/) allows users to disable the laptop keyboard [when specific (or any) external keyboards](https://karabiner-elements.pqrs.org/docs/manual/configuration/disable-built-in-keyboard/) are plugged in. 

TODO - screenshot of disabled Technik

## Footnotes
[^1]: On second thought, I guess it doesn't really matter whether or not I can see the keyboard keys, because you're not supposed to look down at your keyboard when typing. I like to experiment with my keymap every now and then though, and it helps sometimes to look down when I'm familiarizing myself with a new layout. 
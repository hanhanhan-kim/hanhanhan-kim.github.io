---
excerpt: "My first true wireless split keyboard build."
tags: 
    - HIDs
    - Builds
---

In this post, I document my build of a wireless version of the popular [Corne](https://github.com/foostan/crkbd) split keyboard. I found this [post](https://github.com/jhelvy/wireless-corne/tree/main/build) to be very helpful, while I was building my wireless Corne. I talk about the changes I made to the original Corne keyboard, and the changes I wish I had made, if I was doing this build again. 

## Electronics
Most of my parts come from [boardsource.xyz](boardsource.xyz). The only parts I did not get from them are the case, the Mill-Max sockets and pins, and the SPDT slide switches. Most of the soldering in this build is SMD, and so I highly recommend using solder paste and a hot air soldering gun. Angled tweezers help a lot too. Only the µCs are soldered with a soldering iron. 

1. **Solder the diodes.** It’s not so bad, but the ones that came from Boardsource are cylindrical, and tend to roll. The pieces tend to more or less fall into places once heat is added to the solder paste. 

    {% include figure image_path="/assets/images/posts/2022-07-21-wireless-low-profile-corne-build/fig-0.png" alt="" caption="I apply the solder paste first with a syringe, and then I stick the diodes on. I then blast it with the hot air solder gun, and things more or less work out! Sometimes I have to use the tweezers to hold the diodes in place, so they don’t roll around." %}

2. **Solder the hot swap choc switches.** Add solder paste onto all the pads, and then press in the choc switches. They should press in with a fairly snug fit. Then use the heat gun to melt the solder paste onto the hot swap pads. 

    {% include figure image_path="/assets/images/posts/2022-07-21-wireless-low-profile-corne-build/fig-1.png"%}

3. **Solder the low-profile Mill-Max sockets.** I got these sockets from Digikey ([ED5624-ND](https://www.digikey.com/en/products/detail/mill-max-manufacturing-corp/115-93-624-41-003000/81896)). I soldered them onto the PCB with a regular soldering iron and a roll of flux-core solder. 

    {% include figure image_path="/assets/images/posts/2022-07-21-wireless-low-profile-corne-build/fig-2.png" alt="" caption="There’s a TRRS jack in this photo, because I was absent-mindedly assembling things. But because I’m doing a wireless build, I removed the TRRS jack later." %}

4. **Add the Mill-Max pins.** Alternatively, you can use the leftover legs of through-hole diodes that are common for a lot of keyboard builds. But I think the Mill-Max pins are a lot better, just because they're so much sturider. When adding the Mill-Max pins, it helps to use some needle-nose pliers to hold the pins, and then push them into the sockets. 

    {% include figure image_path="/assets/images/posts/2022-07-21-wireless-low-profile-corne-build/fig-3.png" alt=""%}

5. **Place the batteries, and then the nice!nano µCs on top.** The 301230r batteries (110mAh) are the perfect length-width dimensions for slipping underneath Pro Micro-sized microcontrollers. The batteries will add a little height, however, which is why we’re placing them underneath the microcontroller before, soldering the microcontrollers in place. Make sure the wires of the battery are facing the south side of the PCB, like in the photo below. Once you’re happy with the fit, solder on the microcontrollers. 

    {% include figure image_path="/assets/images/posts/2022-07-21-wireless-low-profile-corne-build/fig-4.png" alt=""%}

6. **Siip the battery wires through some unused PCB holes.** For the wireless build, we’re not using the OLED screens, because we want to conserve on battery. We’re also not going to use the TRRS, because this build is wireless. So I just slipped my wires through some of the holes meant for the OLED and the TRRS, as shown below. When slipping the wires through these holes, _no electrical contact should be made_. We’re slipping the wires, just so we can access the bottom side of the PCB. 

    {% include figure image_path="/assets/images/posts/2022-07-21-wireless-low-profile-corne-build/fig-5.png" alt=""%}

7. **Solder the SPDT slide swithces.** This part is a little trickier. In short, we want to install switches that can turn the battery power off, so we can conserve on battery when our keyboard is not in use. The [GitHub link mentioned above](https://github.com/jhelvy/wireless-corne/tree/main/build) is especially useful for this part (underneath the “Assembly” heading). We solder the black GND wire of the battery to the GND pin on the TRRS jack, which is shown in the below photo. We then solder the red VCC wire of the battery to the common (usually the middle) pin of the slide switch. We then solder an adjacent pin on the switch to the RAW pin on the microcontroller, which is also shown in the photo below. In short, we’re inserting a switch between the battery GND and the VCC (RAW). The slide switches I’m using are from Adafruit ([805](https://www.adafruit.com/product/805)). 

    {% include figure image_path="/assets/images/posts/2022-07-21-wireless-low-profile-corne-build/fig-6.png" alt=""%}

## Case
I wanted a case that was low-profile, with a somewhat portable feel. For that reason, I decided to remix [this case](https://www.printables.com/model/117598-travel-crkbd-magnetic-case). I modified this case by getting rid of the TRRS jack slots, and by adding a slot for the SPDT hardware power switch to the battery. My modified case can be downloaded [here](https://www.printables.com/model/245118-corne-wireless-case). 

{% include figure image_path="/assets/images/posts/2022-07-21-wireless-low-profile-corne-build/fig-7.png" alt="" caption="A render of my remixed case."%}

I printed the case in [ColorFabb's woodfill PLA](https://colorfabb.com/woodfill). I then processed the case as described on Justine Haupt's [excellent blog post](https://www.justine-haupt.com/Concertina/). In short, I used coarse 60 grit sandpaper to generate pseudo-'grains'. I then stained the case with some [cheap wood stain](https://www.amazon.com/gp/product/B08CXDRVFQ/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1), and added some polyurethane coats for protection and aesthetics. 

<figure class="half">
    <a href="/assets/images/posts/2022-07-21-wireless-low-profile-corne-build/fig-8.png"><img src="/assets/images/posts/2022-07-21-wireless-low-profile-corne-build/fig-8.png"></a>
    <a href="/assets/images/posts/2022-07-21-wireless-low-profile-corne-build/fig-9.png"><img src="/assets/images/posts/2022-07-21-wireless-low-profile-corne-build/fig-9.png"></a>
    <figcaption>After sanding the case with dry 60 grit sandpaper, I stained the case with multiple coats of wood stain. I then added some polyurethane coats to the case. I think I applied something like 3 coats.</figcaption>
</figure>

## Finishing Touches

I added some choc purpz (25 g) switches, as well as some MBK low profile keycaps. 

<figure class="half">
    <a href="/assets/images/posts/2022-07-21-wireless-low-profile-corne-build/fig-10.png"><img src="/assets/images/posts/2022-07-21-wireless-low-profile-corne-build/fig-10.png"></a>
    <a href="/assets/images/posts/2022-07-21-wireless-low-profile-corne-build/fig-11.png"><img src="/assets/images/posts/2022-07-21-wireless-low-profile-corne-build/fig-11.png"></a>
</figure>

I use M2.5 x 6 mm screws to screw the PCB into the integrated standoffs of the case. I think M2.5 is a little coarser than the intended threads for the case, but I was too lazy to make threads properly, so I just used the screws to shoddily ‘self-tap’ threads into the wood PLA. This lazy 'self-tapping' works out, just because PLA (even composites) are quite soft. I also use M2 x 10 mm + 6 mm (x length of standoff + length of threads), brass, to hold up the top covers that hide the µCs. 

{% include figure image_path="/assets/images/posts/2022-07-21-wireless-low-profile-corne-build/fig-12.png" alt="" caption="The brass standoffs that will hole up the top covers"%}

I also added a very small dab of hot glue to prevent the slide switches from getting pushed too far back into the case with repeated use. 

{% include figure image_path="/assets/images/posts/2022-07-21-wireless-low-profile-corne-build/fig-13.png" alt=""%}

## Admire Your Work!
Tada! :tada: Admire your good work! Use [ZMK](https://zmk.dev/) to upload firmware, and you should be good to go!

{% include figure image_path="/assets/images/posts/2022-07-21-wireless-low-profile-corne-build/fig-14.jpg" alt=""%}
{% include figure image_path="/assets/images/posts/2022-07-21-wireless-low-profile-corne-build/fig-15.jpg" alt=""%}
{% include figure image_path="/assets/images/posts/2022-07-21-wireless-low-profile-corne-build/fig-16.jpg" alt=""%}

## Future Improvements
I think I'd make the following improvements, if I had to do this build again:

- I didn't talk about the magnets I added inside this build. That's because they didn't really work out. Next time, I'd have to edit the casae so that the recesses for the magnets are larger--the polyurethane coat adds a bit of thickness, but I think the original source file's recesses aren't large enough--at least for my liking. I should also purchase stronger magnets, maybe some very legit ones from [K & J Magnetics](https://www.kjmagnetics.com/).
- I think I'd print the top cover with a textured bed, just so it matches the kind of 'matte' vibe of the rest of the case. I could also potentially change the design, so that the top cover 'spills' onto the sides as well a little bit. 
- I'd use black instead of brass M2 screws to secure the top cover onto the keyboard. Again, for aesthetic purposes. 
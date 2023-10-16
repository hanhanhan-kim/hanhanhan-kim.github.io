---
title: Building a Custom Steam Console
tags:
    - Computers
    - Builds
excerpt: ":space_invader: Building a custom gaming console (which is really an SFFPC)."
header:
    og_image: /assets/images/posts/2022-12-03-building-a-steam-console/0.jpg
    teaser: /assets/images/posts/2022-12-03-building-a-steam-console/0.jpg
    header: /assets/images/posts/2022-12-03-building-a-steam-console/0.jpg
    overlay_image: /assets/images/posts/2022-12-03-building-a-steam-console/0.jpg
---

I've been on a bit of a SFFPC-building streak, so I figured why not build another one? I've been curious about HoloISO, which is a port of the official Steam OS image, except it's not tied to the Steam Deck hardware. HoloISO is mostly hardware agnostic, except for its poor support for Nvidia GPUs. For that reason, I thought I would build with an AMD GPU (Steam Deck's poor Nvidia support makes sense, given that the Steam Deck is using a special AMD APU). I also wanted to try a build where I swap out the stock GPU fans for fancy Noctua fans. With these two goals in mind, I ordered some parts and built my custom SFFPC gaming console. 

## The Case

For this build, I've gone with the compact and sleek Velka 5. This case is reliably in stock, and has decent pricing for a SFFPC case. The Velka 5 can also support a full-sized graphics card. 

<figure class="third">
    <a href="/assets/images/posts/2022-12-03-building-a-steam-console/case-0.jpg"><img src="/assets/images/posts/2022-12-03-building-a-steam-console/case-0.jpg"></a>
    <a href="/assets/images/posts/2022-12-03-building-a-steam-console/case-1.jpg"><img src="/assets/images/posts/2022-12-03-building-a-steam-console/case-1.jpg"></a>
    <a href="/assets/images/posts/2022-12-03-building-a-steam-console/case-2.jpg"><img src="/assets/images/posts/2022-12-03-building-a-steam-console/case-2.jpg"></a>
    <figcaption>The Velka 5 case! Very sturdy build, and a great size.</figcaption>
</figure>

The build quality is pristine, and all the parts are extremely sturdy. I'm excited to build in the Velka!

## Testing the Power Supply

Just like with my [last SFFPC build](/building-a-vsffpc), I'm using a [600 W ENP-7660B flex PSU](https://densium.net/products/enp) from Enhance. This PSU is non-modular, so I'm going to have to cut some unnecessary cables, down the road. For now, however, I'm leaving all the cables intact. 

Like with all my builds, I start by testing the functionalisty of the power supply. I plug in a cheap [power supply tester](https://www.amazon.com/gp/product/B076CLNPPK/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1), and check that all the voltage readings are as expected. 

{% include figure image_path="/assets/images/posts/2022-12-03-building-a-steam-console/psu-0.jpg" caption="Looks like the PSU is totally functional!"%} 

## Assembling the Motherboard

For my motherboard, I'm using an [ASRock H610M-ITX/ac](https://www.asrock.com/mb/Intel/H610M-ITXac/index.asp) mini ITX motherboard with an LGA 1700 Intel socket. Accordingly, I'm using a [12th Gen Alder Lake Intel i5-12400F (4.40 GHz)](https://ark.intel.com/content/www/us/en/ark/products/134587/intel-core-i512400f-processor-18m-cache-up-to-4-40-ghz.html). From what I can tell, the i5 is currently [a kind of a sweet spot for price to gaming performance](https://www.youtube.com/watch?v=nhlhA9AnT_s), so it should handle most games I throw, without much issue. 

<figure class="third">
    <a href="/assets/images/posts/2022-12-03-building-a-steam-console/mobo-0.jpg"><img src="/assets/images/posts/2022-12-03-building-a-steam-console/mobo-0.jpg"></a>
    <a href="/assets/images/posts/2022-12-03-building-a-steam-console/mobo-1.jpg"><img src="/assets/images/posts/2022-12-03-building-a-steam-console/mobo-1.jpg"></a>
    <a href="/assets/images/posts/2022-12-03-building-a-steam-console/mobo-2.jpg"><img src="/assets/images/posts/2022-12-03-building-a-steam-console/mobo-2.jpg"></a>
    <figcaption>The motherboard assembly. The first photo shows off the motherboard and all its sockets. The second photo depicts the motherboard with the CPU installed. The final photo shows the CPU cooler, RAM, SSD, and PCIe riser installed. I later swap out the PCIe cable, however, because the depicted cable does not support PCIe 4.0.</figcaption>
</figure>

For the the CPU cooler, I'm using a [Noctua NH-L9i-17xx](https://noctua.at/en/nh-l9i-17xx). This CPU cooler is super quiet and low-profile, and even though it's considered a lighter CPU cooler, it should be sufficient for the 12th gen i5 CPU. I applied a conservative amount of CPU cooling paste on the CPU. 

For RAM, I'm using 2 x 16 GB of [Corsair LPX Vengeneace DDR4 3200 MHz](https://www.corsair.com/us/en/Categories/Products/Memory/VENGEANCE-LPX/p/CMK32GX4M2B3200C16) and for the SSD, I'm using [2 TB of Western Digital WD_BLACK SN770 M.2](https://www.westerndigital.com/products/internal-drives/wd-black-sn770-nvme-ssd#WDS200T3X0E). 

In all my photos, I depict the default Velka PCIe riser, which supports strictly PCIe 3.0. My motherboard, however, doesn't support PCIe 3.0, and so I wound up replacing the riser with the [Velka VC-S290G4 290 mm PCIe 4.0 cable](https://www.velkase.com/products/290-mm-pcie-gen-4-riser-cable), after I ran into some boot issues. I felt a little silly running into the boot issues, because I knew beforehand that PCIe 3.0/4.0 GPU/riser cable incompatibilities result in boot issues, which is why I bought a PCIe 4.0 cable for my [last build](/building-a-vsffpc/#assembling-the-motherboard). 

At this point, I had assembled all the components onto the motherboard. I then moved the motherboard assembly into the case. 

<figure class="half">
    <a href="/assets/images/posts/2022-12-03-building-a-steam-console/mobo-3.jpg"><img src="/assets/images/posts/2022-12-03-building-a-steam-console/mobo-3.jpg"></a>
    <a href="/assets/images/posts/2022-12-03-building-a-steam-console/mobo-4.jpg"><img src="/assets/images/posts/2022-12-03-building-a-steam-console/mobo-4.jpg"></a>
    <figcaption>The first photo shows a top view of the motherboard assembly in the case. The last photo shows a rear view of the motherboard assembly in the case. </figcaption>
</figure>

## Deshrouding, Modifying, and Installing the GPU

From my experience, stock GPU fans leave a lot to be desired. I wanted to try my hand at GPU deshrouding 

## Installing the Power Supply

I now needed to provide power to all my components. I placed my [fully functioning PSU](#testing-the-power-supply) into the allocated spot in my PC case.

<figure class="half">
    <a href="/assets/images/posts/2022-12-03-building-a-steam-console/mobo-5.jpg"><img src="/assets/images/posts/2022-12-03-building-a-steam-console/mobo-5.jpg"></a>
    <a href="/assets/images/posts/2022-12-03-building-a-steam-console/mobo-6.jpg"><img src="/assets/images/posts/2022-12-03-building-a-steam-console/mobo-6.jpg"></a>
    <figcaption>The first photo shows a rear view of the assembly and the second photo shows a top view of the assembly.</figcaption>
</figure>


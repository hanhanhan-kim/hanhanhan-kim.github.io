---
title: Fixing the Very Hot Faucet
tags: 
    - Builds
    - Home
excerpt: A functional, but perhaps janky, home improvement. 
---

The place I'm living in is very old, and has some antiquated housing features. Notably, the hot and cold faucets of my washroom are separated, so achieving a comfortable water temperature is near impossible. 

{% include figure image_path="/assets/images/posts/2022-08-06-fixing-my-very-hot-faucet/0-problem.jpg" alt="" caption="**My problem**. Even with the [faucet extender](https://www.amazon.com/gp/product/B07MB5PTNG/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1) on the hot water side, the water from the hot and cold faucets do not mix. Installing extenders on both faucets severely limits the sink's usable area, and it also does not mix the water streams very well." %}

For a while, implementing an extender on the hot water faucet was a sufficient solution, because the hot water used to be very tame. I could crank up the hot water faucet as much I wanted, and the resulting water temperature would reach a comfortable warmth. Recently, however, a building-wide plumbing 'repair' overcorrected the faucet's hot water temperature. Now, even a small adjustment of the handle results in a skyrocketing water temperature increase. 

{% include figure image_path="/assets/images/posts/2022-08-06-fixing-my-very-hot-faucet/0-hot.jpg" alt="" caption="**Some scalding hot water**. My temperature gun, which I got for free during the heart of the pandemic, suggests a 53.5 C surface temperature. In other words, the water is a little too hot for a human hand." %}

I thought that designing and building a 3D-printed solution would be both fun and useful. I began by estimating the faucet dimensions. 

{% include figure image_path="/assets/images/posts/2022-08-06-fixing-my-very-hot-faucet/1-0-faucet-trace.jpg" alt="" caption="**Making measurements**. I used a pen and a sticky note to trace the shape of the faucet onto the paper. The faucet appeared to terminate in the shape of a rectangle with very rounded corners." %}

{% include figure image_path="/assets/images/posts/2022-08-06-fixing-my-very-hot-faucet/1-1-faucet-trace.jpg" alt="" caption="I used a caliper to measured the traced lengths and widths of the rectangle, as well as the radii of the rounded corners. The inaccuracy of the drawing was probably going to result in an inacurate model." %}

With these measurements, I drafted a quick model that would test the fit of my piece against the faucets' ends. I decided I was going to print the model in PETG, because it's pretty easy to print, and is more heat and humidity-resistant than PLA. In order to ensure a snug fit between the 3D-printed parts and the metal faucet ends, I opted to incorporate an intermediate o-ring into the model. I got [this handy o-ring assortment](https://www.homedepot.com/p/DANCO-200-Piece-O-Ring-Kit-34443/100135126) from a Home Depot trip. I found that the size 12 o-ring made a good fit against the faucet ends, so I based my design on those rings sizes. I printed the test fit piece in a loud yellow colour. 

{% include figure image_path="/assets/images/posts/2022-08-06-fixing-my-very-hot-faucet/2-first-test-fit.jpg" alt="" caption="**First test fit**. Looks like the height and width are a little too large (maybe by about 1 mm, for each?), and the filleted corners are not filleted enough." %}

The first test piece was a little too loose, and the piece failed to fit snugly against the faucet end. So I made some minor adjustments, and tada! The second test fit piece came out perfect :tada:!

{% include figure image_path="/assets/images/posts/2022-08-06-fixing-my-very-hot-faucet/3-0-good-fit.png" alt="" caption="**A second test fit attempt**. The new dimensions of the test piece." %}

{% include figure image_path="/assets/images/posts/2022-08-06-fixing-my-very-hot-faucet/3-1-good-fit.jpg" alt="" caption="**A print of the model**. The second attempt at the test piece fits snugly with the no. 12 o-ring." %}

Now that the part involving the most trial and error was complete, I measured out the approximate range of lengths that might fit between the faucet ends and the middle of the sink. I then drafted and printed a model with the corresponding measurements. 

{% include figure image_path="/assets/images/posts/2022-08-06-fixing-my-very-hot-faucet/4-dist-from-centre.png" alt="" caption="**A model with an acceptable faucet extension length**. I terminate the extension with a circular shape, because I want to be able to implement threading. I later wind up abandoning such a lofty aspiration, in favour of another o-ring-mediated junction." %}

{% include figure image_path="/assets/images/posts/2022-08-06-fixing-my-very-hot-faucet/5-first-extension.jpg" alt="" caption="**A print of the model**. I didn't realize that I can't just lengthen the extension straight-out ... the piece terminates right into the middle of the sink! I have to adjust the 'yaw' angle of the model." %}

The piece was fine, minus the fact that I didn't add any angle to the 'yaw', if we label the water's downward flow as the z-axis. So I added to the piece, a twist about the z-axis. This way, I should end up with more usable sink space. 

{% include figure image_path="/assets/images/posts/2022-08-06-fixing-my-very-hot-faucet/6-complicated-geometry.png" alt="" caption="**A twist**. I am very pleased with myself." %}

{% include figure image_path="/assets/images/posts/2022-08-06-fixing-my-very-hot-faucet/7-good-extension.jpg" alt="" caption="**A print of the model**. Seems to be functional!" %}

I think the resultant piece is pretty successful! I printed a mirrored copy for the other faucet. 

{% include figure image_path="/assets/images/posts/2022-08-06-fixing-my-very-hot-faucet/8-mirrored.jpg" alt="" caption="**A working prototype**. The hot and cold water mix successfully! But there's still room for improvement ...." %}

The mixing of the hot and cold water is pretty good, but not great. I think if I add a third piece that joins the two faucet extenders, and acts kind of like a tee junction, I'll get a pretty decent mixing event in the middle. Back to CAD land!

{% include figure image_path="/assets/images/posts/2022-08-06-fixing-my-very-hot-faucet/9-0-fitting-2-parts.png" alt="" caption="**The joint between an extender and the tee junction**. I plan for another o-ring to generate a seal at the joint." %}

{% include figure image_path="/assets/images/posts/2022-08-06-fixing-my-very-hot-faucet/9-1-fitting-3-parts.png" alt="" caption="**The tee junction**. A shot of the designed tee junction. It has a hole in the middle that the water will exit from, upon mixing." %}

{% include figure image_path="/assets/images/posts/2022-08-06-fixing-my-very-hot-faucet/9-2-entire.png" alt="" caption="**A mock-up of the assembly**. I think it looks promising." %}


+++
date = '2026-06-15T08:46:26-07:00'
draft = false
title = 'Deskus Maximus'
tags = ["design", "decor"]
+++

{{< figure src="/images/deskus.jpeg" caption="What we code in this life echoes through eternity." alt="Deskus Maximus" >}}

This is by far the silliest and most inconsequential project I've ever done, and that's saying something.  I wanted to decorate my desk at my new(-ish) job, and the usual host of succulent planters and fidget toys just weren't going to cut it - my new gig is far too cool for that.  Also, I love architecture, and what would be a better monument to durable engineering than the Colisuem?

Side note: the Latin word for desk is _mensa_.  But there's also the Mensa organization, and I am definitely not a member.  So the far goofier _Deskus Maximus_ it shall be.

### Design

As usual, I fired up OnShape, and imported a simple open-source model of a classical archway.  After patching it up and simplifying it, I separated it into multiple parts for multicolor printing: the main structure in a matte sandstone, and the columns and arch stones in a fun speckled white "marble" filament.  Then I created six variations of the arch, including tabs and slots so they'd fit together, and versions that mitered together in the corners.  Well, to be specific, I didn't create six actual versions of the arch - I just created one, and used [dynamic suppression](https://cad.onshape.com/help/Content/PartStudio/features_and_parts_lists.htm#dynamic_suppression) to parametrically modify it as needed.  One of the best parts of these projects is learning cool new OnShape features.

{{< figure src="/images/onshape-arch.png" alt="Deskus Maximus" >}}


I then designed brick-texture "walkways" that the arches fit into.  For those, I found a brick-red filament with stone-like flecks in it.

{{< figure src="/images/deskus1.jpg" alt="Deskus Maximus" >}}

{{< figure src="/images/deskus8.jpg" alt="Deskus Maximus" >}}


### Are You Not Entertained?

It's not desk decor without electronics and optics.  I used the Waveshare ESP32-S3 1.3inch Display Dev Board with an included 1-inch beamsplitter to create a "floating" image at each end of the second tier.  That meant running wire through the lower tier to a USB-C connector in the back. I wrote a bit of code to display an animated flame while I'm at my desk.  Coming soon: it turns into a flaming skull when a build breaks (it does have WiFi).

{{< figure src="/images/deskus3.jpg" alt="Deskus Maximus"  >}}

<div style="display: flex; gap: 1rem;">
  <video controls>
    <source src="/videos/deskus-maximus.mp4" type="video/mp4">
  </video>
</div>


### Touching Grass

I got to thinking about the desktop itself.  Why are desks flat?  So you can write on them.  Well, I do exactly zero writing duting my workday, and I don't even need a flat surface for a mouse, since I use a trackball.  Not only are trackballs easier on your metacarpals and a delight to use, but they remind me of playing _Missile Command_.  The point is, I don't need a flat desk, so why not turn my desk into a lush, verdant lawn?  Okay fine, lush verdant astroturf, but it beats fake birch veneer.

{{< figure src="/images/deskus9.jpg" alt="Deskus Maximus" >}}

{{< figure src="/images/deskus10.jpg" alt="Deskus Maximus" >}}

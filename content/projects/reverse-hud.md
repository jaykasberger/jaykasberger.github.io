+++
date = '2026-03-15T08:46:26-07:00'
draft = false
title = 'Reverse HUD'
tags = ["hardware", "maker", "XIAO"]
+++

{{< figure src="/images/reverse-hud-clock.jpg" caption="Yes, I own a plastic head, and you should too." alt="reverse HUD" >}}

I was lucky enough to score an invitation to the Pi Day "Mars Colony Program" party, hosted by the 
wonderful and innovative people at [Pebblebed Ventures](https://pebblebedventures.com).  Pebblebed transformed their workspace into a Mars exploration facility, asking us (in writing, even!) to suspend our disbelief and contemplate our impending journey to the Red Planet.  The activity stations were surprisingly, delightfully philosophical in nature, and the atmosphere they created was nothing short of transformative.  Super fun, but it was also one of the most _thoughtful_ events I've attended in a long, long time.

Participants were required to dress entirely in red.  I bought some garish red pants I'll probably never wear again, and they were still worth every penny.  Since we were asked to bring one thing we'd either leave on Earth or take to Mars, I decided to build a bit of tech I'd need on the journey, and maybe make a bit of a statement in the process.

### The Idea

Heads-up displays (HUDs) are a staple of sci-fi cool.  Fighter helmets, Terminator eyes, cyberpunk mods: they appeal to the power fantasy of seeing what everyone else cannot, of having knowledge floating right in front that's just for you.  I'd even say the "detection" sequences in the BBC's _Sherlock_ are a form of HUD, except what's powering Sherlock's HUD is superhuman deduction rather than a CPU.  But the underlying theme is still there.  A heads-up display gives you data and leverage you didn't have before, and presumably that others still don't.  Like so much digital technology, it's about turning information into power.

What if we turned that around, though?  What if we made a HUD that provides data to everyone else?  That would invert the usual technology power dynamic and make the device about sharing instead of personal advantage.

Okay, I'll admit that a lot of this is philosophical retrofitting.  A real, wearable HUD requires fairly complex optics and projection elements.  I don't have the time, money, or expertise to build a waveguide rig or integrate a Micro LED with a prism.  But what I can do is put a trasparent OLED in my field of vision and power it with a microcontroller.

### Parts

{{< figure src="/images/1.51inch-transparent-oled-1.jpg" caption="Waveshare 1.51\" transparent OLED" alt="transparent OLED" >}}

- The Display: I bought [this OLED display from Waveshare](https://www.waveshare.com/1.51inch-transparent-oled.htm). I've used it in earlier projects, and it's a handy little component.  It's only 128x64 and monochrome, but as an OLED the output is super bright and sharp.  Once you pull the plastic protective film off (and who doesn't love doing that?), it's very clear and easy to see through.

{{< figure src="/images/seeed-studio-mg24.jpg" caption="Seeed Studio XIAO MG24 Sense" alt="Seeed Studio XIAO MG24 Sense microcontroller" >}}

- The Microcontroller: [The Seeed Studio XIAO MG24 Sense](https://www.seeedstudio.com/Seeed-XIAO-MG24-Sense-p-6248.html).  Tiny but amazing.  It runs at a mere 78MHz yet did everything I needed with cycles to spare.  It has a six-axis IMU on board, an analog microphone, and BLE.  It even has a DSP and an on-device inference code (basically, accelerated vector math) in case you want to run some very small ML models.  It's eleven dollars. _Eleven dollars._

{{< figure src="/images/enclosure.png" caption="PCTG enclosure designed in OnShape" alt="3D printed enclosure" >}}

- The Enclosure: Designed in [OnShape](https://onshape.com) and printed in PCTG.  It was the only transparent filament I had on hand, and I wanted this thing to be as see-through as possible.  But, it's pretty much the ideal choice, since it's strong, heat-resistant, and easy to print.

- Everything Else:  I used some heat-set inserts and some M3 screws to keep the eyepiece attached to my glasses and stable.  And, I ran a USB-C cable from the MG24 down the back of my Martian red shirt to a battery in my pocket.  The MG24 actually has a battery charging circuit, but, I only had a day to do this and I'm terrible at soldering.

{{< figure src="/images/assembly.jpg" caption="Final check before assembly!  Just kidding, I never check anything." alt="reverse HUD assembly" >}}

### Code and Functionality

With only a day, and also with a shaky foundation in C, I let Claude Code do most of the driving.  Basically, I built in a few modes: 

- an animated starfield (which might remind some vintage Atari enthusiasts of _Star Raiders_)
- a spectrogram of the live audio
- an artificial horizon
- a clock showing the time on Earth and Mars
- a QR code for my [LinkedIn.](https://www.linkedin.com/in/jaykasberger/)  (Yeah, I know.)

Claude did a superb job, of course, but it's always interesting to see the ways in which coding agents fail.  In this case, Claude couldn't quite figure out how to account for the alignment of the components, since the display was in portait mode, and techincally backwards, while the MG24 was installed with a 90° clockwise roll.  Frontier models are getting better at spatial reasoning, but maybe this arrangement was a bit exotic, or maybr I didn't describe it very well.

### The Result

{{< figure src="/images/results.png" caption="Ladies and gentlemen, give it up for Gray Man Group" alt="reverse HUD results" >}}
<div style="display: flex; gap: 1rem;">
  <video controls width="33%">
    <source src="/videos/spectrogram.mp4" type="video/mp4">
  </video>
  <video controls width="33%">
    <source src="/videos/horizon.mp4" type="video/mp4">
  </video>
</div>

In short, the Reverse HUD was a lot of fun and a huge hit.  And, it sparked several conversations about what the tradeoffs we make when we intermediate the connections between ourselves and others with technology.  Most of all, wearing it was my committment to the event's imaginary premise - I built the technology and I was heading to Mars, at least for Pi Day.

Finally, let me extent a huge thanks to the amazing Pebblebed Ventures for hosting the event.  If we do ever get to Mars, it'll be thanks to people like you.

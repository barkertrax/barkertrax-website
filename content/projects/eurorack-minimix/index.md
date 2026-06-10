---
title: "Building Benjiao Modular's Eurorack MiniMix Module"
date: 2026-05-31

summary: "Build log for the Benjiao Eurorack mixer module."

tags:
  - eurorack
  - synth
  - electronics
  - audio

project_status: completed

ShowToc: true
---
# Building Benjiao Modular's Eurorack MiniMix Module

## Goal

* Every eurorack system needs at least one mixer and I don't have any
* Order a known good PCB from an online supplier
* If successful, I'll have the KiCad project, PCB, and front panel as references for future projects, and I'll know a reliable supplier for PCB manufacturing.

## Status

* 95% Complete
* Replace incorrect power filter capacitors with 22 µF parts
* Find some knobs for the slider shafts

## References

* [Benjiao's MiniMix blog post](https://benjiaomodular.com/post/2023-05-24-minimix/)
* [Github Repo for MiniMix](https://github.com/benjiaomodular/MiniMix) - I built the v1.2 revision, which has various fixes to earlier PCBs

## Progress

### 2026-05-05 Built a Second Module

Rinse and repeat. I now own 2 mixers!

### 2026-04-26 Testing

This was where things got semi-interesting.

As the pots weren't throwaway cheap, I figured I'd test one channel before fitting an entire module's worth.

And as my [eurorack bench power supply project](/projects/eurorack-bench-supply/) is still in development, with the breadboard version hooked up to [a different module](/projects/eurorack-quad-vca/) that's also still in development, I chose to use my actual modular system to power the new module. In the cold light of day, this was not a great decision and, whilst nothing went wrong, the balance of risk and reward was way off.

First, I did a simple power-up to check that there was the right amount of power everywhere I expected. An op-amp immediately started smoking. I'd soldered it in upside down.

After a quick switcheroo I routed [Braids](/projects/mutable-intruments-braids/) through the mixer, with the oscilloscope connected before and after MiniMix. Things looked almost right, but not quite. Tracing the signal through, the DC coupling capacitor C7 ([circuit](https://benjiaomodular.com/post/2023-05-24-minimix/images/MiniMix%20v1.1%20-%20Schematics.png)) seemed to be doing something odd to the signal. I bypassed it and all was well so I substituted C7, C5, C6 and C10 with links.

The more I think about this, I feel like something else may be going on and further analysis would make a good article for the site.

### 2026-04-25 Populated a PCB

No dramas here. The [circuit](https://benjiaomodular.com/post/2023-05-24-minimix/images/MiniMix%20v1.1%20-%20Schematics.png) is pretty straightforward, so everything went together quickly.

With all the components in place, I checked continuity against the schematic. Always a vital step as I found a dry joint on an op-amp pin.

### 2026-04-20 Ordered Components

Given that I was working to a PCB that was already laid out, I needed to ensure that the components I ordered would all fit - in particular the sliders. After searching around, I ended up getting everything from DigiKey as they stocked the 45mm travel, 100k Bourns sliders.

Unfortunately, I ordered the wrong value capacitors for the power supply filters - 0.22uF, rather than 22uF.

### 2026-04-14 Ordered PCBs

For previous projects, I'd used [OSHPark](https://oshpark.com/) but this time around I quite liked the look of [JLCPCB](https://jlcpcb.com/). Cost was surprisingly low and turnaround was really quick. I ordered the minimum of 5 PCBs.

## Outcome

* Module functions correctly despite the missing power filter capacitors
* JLCPCB delivered good-quality boards
* The design was straightforward to assemble
* I made a couple of avoidable mistakes during assembly and testing
* I'd happily build another one
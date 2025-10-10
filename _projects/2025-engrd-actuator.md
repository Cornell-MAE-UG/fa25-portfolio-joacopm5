---
layout: project
title: Maximizing Mechanical Advantage
description: Portfolio Assignment ENGRD 2020
technologies: [Python]
image: /assets/images/radio-machine-cad.jpg
---

In HW4, we were tasked with creating a mechanism consisting of a rigid bar, an actuator, and a payload. Additionally, we were restricted to using only three pins, two of which had to be on the ground. Our objective was to maximize the lift height and load within a workspace of 150 cm x 50 cm. The actuator I selected was the Tolomatic IMA33 with a BN05 lead. The peak thrust for this actuator is 4.45 kN and I chose the stroke length to be 380.8 mm, which is within its stroke range of 76.2 mm to 457.2 mm.

![Shaded rendering of earlier version]({{ "/assets/images/actuator-data.jpg" | relative_url }}){: .inline-image-r style="width: 200px"}

The mechanism consists of a bar of L = 0.608 m and is driven by the actuator at a radius of 0.45 m. The base of the actuator is pinned to the ground at x = 85 cm while the bar is pinned to the ground at x = 45 cm.

If we have the pivot at A, the bar makes an angle θ from the horizontal, and tip load W acts downward a distance L from A. F~act~= acts along its own line at point J a distance r from A along the bar. Then, we can let α be the angle between the bar and the actuator force, or between $\mathbf{r}$~j~ and $\mathbf{F}$~act~.

If we take moments about A, we get that:
   WLcos(θ) = F~act~rsin(α)
    W = F~act~(r/L)(sin(α)/cos(θ)).

And, the height change:
    Δh ≈ L(sinθ~2~-sinθ~1~)

So, with F~act~ = 4.45 kN, α = 62 deg (using Law of Sines), θ = 57 deg, r = 0.45 m, L = 0.61 m:
    W = 5.3 kN
So, mechanical advantage W/F~act~ = 1.2

In order to maximize the mechanical advantage, we have to forego lift. However, some things we could do are increase te bar length, allowing more stroke, or getting a bigger actuator.

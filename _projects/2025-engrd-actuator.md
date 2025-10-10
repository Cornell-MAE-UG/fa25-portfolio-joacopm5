---
layout: project
title: Maximizing M.A. to Lift Ratio
math: true
description: Portfolio Assignment ENGRD 2020
technologies: [LaTeX, AI to convert raw calculations into LaTeX format]
image: /assets/images/actuator-sketch.jpg
---
In HW4, we were tasked with creating a mechanism consisting of a rigid bar, an actuator, and a payload. Additionally, we were restricted to using only three pins, two of which had to be on the ground. Our objective was to maximize the lift height and load within a workspace of $150\,\text{cm}\times 50\,\text{cm}$. The actuator I selected was the Tolomatic IMA33 with a BN05 lead. The peak thrust for this actuator is $4.45\,\mathrm{kN}$ and I chose the stroke length to be $380.8\,\mathrm{mm}$, which is within its stroke range of $76.2\,\mathrm{mm}$ to $457.2\,\mathrm{mm}$.



The mechanism consists of a bar of $L = 0.608\,\text{m}$ and is driven by the actuator at a radius of $r = 0.45\,\text{m}$. The base of the actuator is pinned to the ground at $x = 85\,\text{cm}$ while the bar is pinned to the ground at $x = 45\,\text{cm}$.

![Shaded rendering of earlier version]({{ "/assets/images/actuator-data.jpg" | relative_url }}){: .inline-image-r style="width: 350px"}

If we have the pivot at $A$, the bar makes an angle $\theta$ from the horizontal, and tip load $W$ acts downward a distance $L$ from $A$. $F_{\text{act}}$ acts along its own line at point $J$ a distance $r$ from $A$ along the bar. Then, we can let $\alpha$ be the angle between the bar and the actuator force, between $\vec r_{j}$ and $\vec F_{\mathrm{act}}$.





**Moment about $A$:**
$$
W\,L\cos\theta \;=\; F_{\text{act}}\,r\sin\alpha
\quad\Rightarrow\quad
W \;=\; F_{\text{act}}\left(\frac{r}{L}\right)\left(\frac{\sin\alpha}{\cos\theta}\right).
$$

**Height change:**
$$
\Delta h \approx L\big(\sin\theta_2 - \sin\theta_1\big).
$$

(with $L=0.608\,\text{m}$, $\theta_1 \approx 29.5^\circ$, $\theta_2 \approx 80^\circ$): $\displaystyle \Delta h \approx 0.299\,\text{m}$.

With $F_{\text{act}} = 4.45\,\text{kN}$, $\alpha = 62^\circ$ (Law of Sines), $\theta = 57^\circ$, $r = 0.45\,\text{m}$, $L = 0.61\,\text{m}$:
$$
W \approx 5.3\,\text{kN}, \qquad \frac{W}{F_{\text{act}}} \approx 1.2.
$$

To maximize the **M.A.–to–lift ratio** (force gain per mm of vertical lift), we place the actuator base so $\alpha$ is nearly perpendicular at the heaviest part of the lift, keep the bar’s rotation modest to use the stroke efficiently, and choose a large attach radius ($r/L \approx 0.7$–$0.8$). With the fixed $380.8\,\mathrm{mm}$ stroke, select $[\theta_1,\theta_2]$ to fully use the stroke while maximizing the minimum M.A.–to–lift ratio over that heavy-lift interval.












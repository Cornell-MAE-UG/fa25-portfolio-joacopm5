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

(with $L=0.608\,\text{m}$, $\theta_1 \approx 9.46^\circ$, $\theta_2 \approx 56^\circ$): $\displaystyle \Delta h \approx 0.41\,\text{m}$.

With $F_{\text{act}} = 4.45\,\text{kN}$, $\alpha = 62^\circ$ (Law of Sines), $\theta = 57^\circ$, $r = 0.45\,\text{m}$, $L = 0.61\,\text{m}$:
$$
W \approx 5.3\,\text{kN}, \qquad \frac{W}{F_{\text{act}}} \approx 1.2.
$$

To maximize the **M.A.–to–lift ratio** (force gain per mm of vertical lift), we have to place the actuator base so that $\alpha$ is almost perpendicular when the actuator has to raise the largest load. We also want to reduce rotation to maximize how much stroke we use. Finally, we want a large radius of attachment ($r/L \approx 0.7$–$0.8$). With the fixed $380.8\,\mathrm{mm}$ stroke, we choose $[\theta_1,\theta_2]$ to use the stroke while maximizing the minimum M.A.–to–lift ratio over that period of largest effective load.

Now, we no longer consider the bar to be rigid, so we use Euler–Bernoulli beam theory to analyze how this changes the problem.

We focus on the worst-case configuration used to maximize mechanical advantage when the beam was rigid:
$$
\theta \approx 57^\circ, 
\qquad
\alpha \approx 62^\circ,
\qquad
W \approx 5.3\,\text{kN},
\qquad
F_{\mathrm{act}} = 4.45\,\text{kN}.
$$

To apply Euler–Bernoulli beam theory, we assume that deflections are small, the flexural rigidity $EI$ is constant along the span of the bar, and only the components of $W$ and $F_{\mathrm{act}}$ perpendicular to the beam contribute to bending. For a conservative estimate of the deflection, we model the bar as a cantilever fixed at $A$ and free at its tip.

The perpendicular components of the loads are therefore
$$
W_\perp = W\cos\theta,
\qquad
F_\perp = F_{\mathrm{act}}\sin\alpha.
$$

Numerically,
$$
W_\perp \approx 2.89\times 10^3\,\text{N},
\qquad
F_\perp \approx 3.93\times 10^3\,\text{N}.
$$

Using the cantilever beam formulas for (1) a point load $W_\perp$ at the free end and (2) a point load $F_\perp$ applied at a distance $r$ from the fixed end, the maximum tip deflection is
$$
\delta_{\max}
=
\frac{W_\perp L^3}{3EI}
+
\frac{F_\perp\,r^2(3L - r)}{6EI}.
$$

Substituting $L = 0.608\,\text{m}$ and $r = 0.45\,\text{m}$ gives
$$
\delta_{\max} = \frac{398.5}{EI}.
$$

The project requirement is that the beam’s vertical deflection must remain below $2\%$ of its length:
$$
\delta_{\max} \le 0.02L = 0.0122\,\text{m}.
$$

Therefore, the beam must satisfy
$$
EI \ge \frac{398.5}{0.0122}
\approx 3.28\times 10^4\,\text{N}\cdot\text{m}^2.
$$

To design the lightest possible beam, we compare aluminum and steel. The minimum required second moment of area for each is
$$
I_{\min,\mathrm{Al}}
=
\frac{3.28\times 10^4}{70\times 10^9}
\approx 4.7\times 10^{-7}\,\text{m}^4,
\qquad
I_{\min,\mathrm{st}}
=
\frac{3.28\times 10^4}{200\times 10^9}
\approx 1.64\times 10^{-7}\,\text{m}^4.
$$

A rectangular hollow tube is a good candidate because it achieves high stiffness for low mass. For a tube with outer dimensions $b \times h$ and wall thickness $t$,
$$
I = \frac{1}{12}\big(bh^3 - (b - 2t)(h - 2t)^3\big),
\qquad
A = bh - (b - 2t)(h - 2t).
$$

A mass-efficient aluminum choice that meets the stiffness requirement is
$$
h = 100\,\text{mm},
\qquad
b = 20\,\text{mm},
\qquad
t = 2\,\text{mm}.
$$

For this cross-section,
$$
I \approx 4.87\times 10^{-7}\,\text{m}^4,
\qquad
A \approx 4.64\times 10^{-4}\,\text{m}^2.
$$

The mass of the beam is
$$
m_{\mathrm{Al}}
=
\rho_{\mathrm{Al}} A L
=
2700 \times 4.64\times 10^{-4} \times 0.608
\approx 0.76\,\text{kg}.
$$

The expected maximum deflection is then
$$
\delta_{\max,\mathrm{Al}}
=
\frac{398.5}{E_{\mathrm{Al}} I}
\approx 0.0117\,\text{m}
\approx 1.9\%\,L,
$$
which satisfies the $2\%$ limit.

$$
\boxed{
\text{Final beam selection: Rectangular aluminum tube } 
(100\,\text{mm} \times 20\,\text{mm} \times 2\,\text{mm}),\quad
L = 608\,\text{mm}.
}
$$

A schematic of the final beam cross-section and its placement within the mechanism is shown in the figure below.

![Final beam design sketch]({{ "/assets/images/beam-design.jpg" | relative_url }}){: style="max-width:100%; width:300px; height:auto; display:block; margin:0 auto;"}


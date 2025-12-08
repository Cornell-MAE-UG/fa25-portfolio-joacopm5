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

𝜃
≈
57
∘
,
𝛼
≈
62
∘
,
𝑊
≈
5.3
 
kN
,
𝐹
a
c
t
=
4.45
 
kN
.
θ≈57
∘
,α≈62
∘
,W≈5.3kN,F
act
	​

=4.45kN.

We also need a few assumptions for our analysis to apply.

Assumptions

Small deflections (Euler–Bernoulli linear theory).

Constant 
𝐸
E and 
𝐼
I along the beam.

Only the force components perpendicular to the beam induce bending.

Conservative modeling: the bar behaves as a cantilever fixed at 
𝐴
A and free at 
𝑥
=
𝐿
x=L.

(a) Maximum Deflection of the Beam

The transverse force components are

𝑊
⊥
=
𝑊
cos
⁡
𝜃
,
𝐹
⊥
=
𝐹
a
c
t
sin
⁡
𝛼
.
W
⊥
	​

=Wcosθ,F
⊥
	​

=F
act
	​

sinα.

Numerically,

𝑊
⊥
≈
2.89
×
10
3
 N
,
𝐹
⊥
≈
3.93
×
10
3
 N
.
W
⊥
	​

≈2.89×10
3
 N,F
⊥
	​

≈3.93×10
3
 N.

Modeling the beam as a cantilever with a tip load and a point load at 
𝑟
r, the maximum deflection is

𝛿
max
⁡
=
𝑊
⊥
𝐿
3
3
𝐸
𝐼
+
𝐹
⊥
𝑟
2
(
3
𝐿
−
𝑟
)
6
𝐸
𝐼
.
δ
max
	​

=
3EI
W
⊥
	​

L
3
	​

+
6EI
F
⊥
	​

r
2
(3L−r)
	​

.

Substituting 
𝐿
=
0.608
 
m
L=0.608m and 
𝑟
=
0.45
 
m
r=0.45m,

𝛿
max
⁡
=
398.5
𝐸
𝐼
.
δ
max
	​

=
EI
398.5
	​

.

The design constraint requires

𝛿
max
⁡
≤
0.02
𝐿
=
0.0122
 m
.
δ
max
	​

≤0.02L=0.0122 m.

Thus,

𝐸
𝐼
≥
398.5
0.0122
≈
3.28
×
10
4
 N
⋅
m
2
.
EI≥
0.0122
398.5
	​

≈3.28×10
4
 N⋅m
2
.
(b) Mass-Efficient Beam Design

The minimum required second moment of area for each material is

𝐼
min
⁡
,
A
l
=
3.28
×
10
4
70
×
10
9
≈
4.7
×
10
−
7
 
m
4
,
I
min,Al
	​

=
70×10
9
3.28×10
4
	​

≈4.7×10
−7
 m
4
,
𝐼
min
⁡
,
s
t
=
3.28
×
10
4
200
×
10
9
≈
1.64
×
10
−
7
 
m
4
.
I
min,st
	​

=
200×10
9
3.28×10
4
	​

≈1.64×10
−7
 m
4
.

For a rectangular hollow tube with outer dimensions 
𝑏
×
ℎ
b×h and thickness 
𝑡
t,

𝐼
=
1
12
(
𝑏
ℎ
3
−
(
𝑏
−
2
𝑡
)
(
ℎ
−
2
𝑡
)
3
)
,
𝐴
=
𝑏
ℎ
−
(
𝑏
−
2
𝑡
)
(
ℎ
−
2
𝑡
)
.
I=
12
1
	​

(bh
3
−(b−2t)(h−2t)
3
),A=bh−(b−2t)(h−2t).

A mass-efficient aluminum section meeting the stiffness requirement is:

ℎ
=
100
 mm
,
𝑏
=
20
 mm
,
𝑡
=
2
 mm
.
h=100 mm,b=20 mm,t=2 mm.

For this cross-section,

𝐼
≈
4.87
×
10
−
7
 
m
4
,
𝐴
≈
4.64
×
10
−
4
 
m
2
.
I≈4.87×10
−7
 m
4
,A≈4.64×10
−4
 m
2
.

The mass is

𝑚
A
l
=
𝜌
A
l
 
𝐴
 
𝐿
=
2700
×
4.64
×
10
−
4
×
0.608
≈
0.76
 kg
.
m
Al
	​

=ρ
Al
	​

AL=2700×4.64×10
−4
×0.608≈0.76 kg.

The resulting deflection is

𝛿
max
⁡
,
A
l
=
398.5
𝐸
A
l
𝐼
≈
0.0117
 m
≈
1.9
%
 
𝐿
,
δ
max,Al
	​

=
E
Al
	​

I
398.5
	​

≈0.0117 m≈1.9%L,

which satisfies the 2% limit.

Final beam selection: Rectangular aluminum tube 
(
100
 mm
×
20
 mm
×
2
 mm
)
,
𝐿
=
608
 mm
.
Final beam selection: Rectangular aluminum tube (100 mm×20 mm×2 mm),L=608 mm.
	​

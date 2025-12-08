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

Now, we no longer consider the bar to be rigid, so we will use Euler--Bernoulli beam
theory to analyze how this changes the problem.

We focus on the worst-case configuration, which is the same configuration used to
maximize the mechanical advantage when the beam was rigid:
\[
\theta \approx 57^\circ, 
\qquad 
\alpha \approx 62^\circ,
\qquad
W \approx 5.3\,\text{kN}, 
\qquad
F_{\mathrm{act}} = 4.45\,\text{kN}.
\]

We also need a few assumptions for our analysis to apply.

\subsection*{Assumptions}
\begin{itemize}
    \item Small deflections (Euler--Bernoulli linear theory).
    \item Constant $E$ and $I$ along the beam.
    \item Only the force components perpendicular to the beam induce bending.
    \item Conservative modeling: the bar is treated as a cantilever fixed at $A$ and free at $x=L$.
\end{itemize}

\subsection*{(a) Maximum Deflection of the Beam}

The transverse components of the forces are
\[
W_\perp = W\cos\theta,
\qquad
F_\perp = F_{\mathrm{act}}\sin\alpha.
\]

Numerically,
\[
W_\perp \approx 2.89\times 10^3\,\text{N},
\qquad
F_\perp \approx 3.93\times 10^3\,\text{N}.
\]

Using the cantilever formulas for a point load at the tip and a point load at an
interior location $r$, the maximum deflection at the free end is
\[
\delta_{\max}
= \frac{W_\perp L^3}{3EI}
+ \frac{F_\perp\, r^2(3L - r)}{6EI}.
\]

Substituting $L = 0.608\,\text{m}$ and $r = 0.45\,\text{m}$ gives
\[
\delta_{\max} = \frac{398.5}{EI}.
\]

The design constraint requires the vertical deflection to remain below $2\%$ of the
beam length:
\[
\delta_{\max} \le 0.02L = 0.0122\,\text{m}.
\]

Thus,
\[
EI \ge \frac{398.5}{0.0122}
\approx 3.28\times 10^4\,\text{N}\cdot\text{m}^2.
\]

\subsection*{(b) Mass-Efficient Beam Design}

To satisfy the stiffness requirement, the minimum second moment of area for each
material is
\[
I_{\min,\mathrm{Al}} 
= \frac{3.28\times 10^4}{70\times 10^9}
\approx 4.7\times 10^{-7}\,\text{m}^4,
\qquad
I_{\min,\mathrm{st}}
= \frac{3.28\times 10^4}{200\times 10^9}
\approx 1.64\times 10^{-7}\,\text{m}^4.
\]

A rectangular hollow tube gives a high stiffness-to-mass ratio. For a tube with outer
dimensions $b \times h$ and wall thickness $t$,
\[
I = \frac{1}{12}\big( b h^3 - (b - 2t)(h - 2t)^3 \big),
\qquad
A = bh - (b - 2t)(h - 2t).
\]

A mass-efficient aluminum section meeting $I \ge I_{\min,\mathrm{Al}}$ is
\[
h = 100\,\text{mm}, 
\qquad 
b = 20\,\text{mm}, 
\qquad 
t = 2\,\text{mm}.
\]

For this configuration,
\[
I \approx 4.87\times 10^{-7}\,\text{m}^4,
\qquad
A \approx 4.64\times 10^{-4}\,\text{m}^2.
\]

The mass is
\[
m_{\mathrm{Al}}
= \rho_{\mathrm{Al}} A L
= 2700 \times 4.64\times 10^{-4} \times 0.608
\approx 0.76\,\text{kg}.
\]

The resulting deflection is
\[
\delta_{\max,\mathrm{Al}}
= \frac{398.5}{E_{\mathrm{Al}}\, I}
\approx 0.0117\,\text{m}
\approx 1.9\%\,L,
\]
which satisfies the $2\%$ requirement.

\[
\boxed{
\text{Final beam selection: Rectangular aluminum tube }
(100\,\text{mm} \times 20\,\text{mm} \times 2\,\text{mm}),
\; L = 608\,\text{mm}.
}
\]

\subsection*{(c) Final Beam Sketch}

A simple schematic of the final beam design is shown below.

\begin{figure}[h!]
\centering
\begin{tikzpicture}[scale=1.1]

% Beam
\draw[thick] (0,0) -- (6,0);
\node at (0,0) {\small $\bullet$};
\node[below] at (0,0) {\small Pivot $A$};

% Actuator attachment
\node at (4.45,0) {\small $\bullet$};
\node[below] at (4.45,0) {\small $J$};

% Tip
\node at (6,0) {\small $\bullet$};
\node[below] at (6,0) {\small Tip};

% Actuator
\draw[thick,red] (4.45,0) -- (8,-1.0);
\node[right] at (8,-1.0) {\small Ground pin};

% Cross-section
\begin{scope}[shift={(0,-2.2)}]
\draw[thick] (0,0) rectangle (2,1);
\draw[thick] (0.2,0.2) rectangle (1.8,0.8);
\node[right] at (2.2,0.5) {\small Cross-section: $100\,$mm $\times$ $20\,$mm, $t = 2\,$mm};
\end{scope}

\end{tikzpicture}
\caption{Final beam design: aluminum rectangular hollow tube with $h = 100\,$mm, $b = 20\,$mm, $t = 2\,$mm, and $L = 608\,$mm.}
\end{figure}











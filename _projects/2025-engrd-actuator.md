---
layout: project
title: Maximizing Mechanical Advantage
description: Portfolio Assignment ENGRD 2020
technologies: [LaTex]
image: /assets/images/actuator-sketch.jpg
---

\documentclass[11pt]{article}
\usepackage{amsmath, amssymb}
\usepackage{graphicx}
\usepackage[margin=1in]{geometry}

\begin{document}

In HW4, we were tasked with creating a mechanism consisting of a rigid bar, an actuator, and a payload. Additionally, we were restricted to using only three pins, two of which had to be on the ground. Our objective was to maximize the lift height and load within a workspace of 150 cm x 50 cm. The actuator I selected was the Tolomatic IMA33 with a BN05 lead. The peak thrust for this actuator is 4.45 kN and I chose the stroke length to be 380.8 mm, which is within its stroke range of 76.2 mm to 457.2 mm.

\begin{figure}[h]
  \centering
  % Shaded rendering of earlier version
  \includegraphics[width=350pt]{/assets/images/actuator-data.jpg}
\end{figure}

The mechanism consists of a bar of \(L = 0.608\ \mathrm{m}\) and is driven by the actuator at a radius of \(0.45\ \mathrm{m}\). The base of the actuator is pinned to the ground at \(x = 85\ \mathrm{cm}\) while the bar is pinned to the ground at \(x = 45\ \mathrm{cm}\).

If we have the pivot at \(A\), the bar makes an angle \(\theta\) from the horizontal, and tip load \(W\) acts downward a distance \(L\) from \(A\). \(F_{\text{act}}\) acts along its own line at point \(J\) a distance \(r\) from \(A\) along the bar. Then, we can let \(\alpha\) be the angle between the bar and the actuator force, or between \(\mathbf{r}_j\) and \(\mathbf{F}_{\text{act}}\).

If we take moments about \(A\), we get that:
\[
  W L \cos(\theta) = F_{\text{act}}\, r \sin(\alpha),
\]
\[
  W = F_{\text{act}}\left(\frac{r}{L}\right)\left(\frac{\sin(\alpha)}{\cos(\theta)}\right).
\]

And, the height change:
\[
  \Delta h \approx L\left(\sin \theta_2 - \sin \theta_1\right).
\]

So, with \(F_{\text{act}} = 4.45\ \mathrm{kN}\), \(\alpha = 62^\circ\) (using Law of Sines), \(\theta = 57^\circ\), \(r = 0.45\ \mathrm{m}\), \(L = 0.61\ \mathrm{m}\):
\[
  W = 5.3\ \mathrm{kN}.
\]
So, mechanical advantage \( \dfrac{W}{F_{\text{act}}} = 1.2\).

In order to maximize the mechanical advantage, we have to forego lift. However, some things we could do are increase the bar length, allowing more stroke, or getting a bigger actuator.

\end{document}

---
layout: project
title: Maximizing Mechanical Advantage
description: Portfolio Assignment ENGRD 2020
technologies: [LaTeX, AI to convert raw calculations into LaTeX format]
image: /assets/images/actuator-sketch.jpg
---

In HW4, we were tasked with creating a mechanism consisting of a rigid bar, an actuator, and a payload. Additionally, we were restricted to using only three pins, two of which had to be on the ground. Our objective was to maximize the lift height and load within a workspace of 150 cm × 50 cm. The actuator I selected was the Tolomatic IMA33 with a BN05 lead. The peak thrust for this actuator is **4.45 kN** and I chose the stroke length to be **380.8 mm**, which is within its stroke range of **76.2 mm to 457.2 mm**.

![Shaded rendering of earlier version]({{ "/assets/images/actuator-data.jpg" | relative_url }})

The mechanism consists of a bar of \(L = 0.608\,\text{m}\) and is driven by the actuator at a radius of \(r = 0.45\,\text{m}\). The base of the actuator is pinned to the ground at \(x = 85\,\text{cm}\) while the bar is pinned to the ground at \(x = 45\,\text{cm}\).

If we have the pivot at \(A\), the bar makes an angle \(\theta\) from the horizontal, and tip load \(W\) acts downward a distance \(L\) from \(A\). \(F_{\text{act}}\) acts along its own line at point \(J\) a distance \(r\) from \(A\) along the bar. Then, we can let \(\alpha\) be the angle between the bar and the actuator force, or between \(\mathbf{r}_j\) and \(\mathbf{F}_{\text{act}}\).

**Moment about \(A\):**
$$
W\,L\cos\theta = F_{\text{act}}\,r\sin\alpha
\qquad\Rightarrow\qquad
W = F_{\text{act}}\left(\frac{r}{L}\right)\left(\frac{\sin\alpha}{\cos\theta}\right).
$$

**Height change:**
$$
\Delta h \approx L\big(\sin\theta_2-\sin\theta_1\big).
$$

With \(F_{\text{act}} = 4.45\,\text{kN}\), \(\alpha = 62^\circ\) (Law of Sines), \(\theta = 57^\circ\), \(r = 0.45\,\text{m}\), \(L = 0.61\,\text{m}\):
$$
W \approx 5.3\,\text{kN}, \qquad \text{so} \quad \frac{W}{F_{\text{act}}} \approx 1.2.
$$

To maximize mechanical advantage, we trade lift-per-stroke (virtual work). Practical levers include increasing the bar length \(L\) within the envelope, allowing more stroke, or selecting a larger actuator.




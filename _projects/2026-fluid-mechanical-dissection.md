---
layout: project
title: "Semester Design Project"
math: true
description: "MAE 2250 - Intro to Mechanical Design"
technologies: "Fusion 360, 3D Printing"
image: "/assets/images/brslogo.png"
fontsize: 11pt
geometry: margin=1in
papersize: letter
pagestyle: empty
header-includes:
 - '\pagenumbering{gobble}'
 - '\usepackage{url}'
 - '\usepackage{enumitem}'
 - '\usepackage{graphicx}'
 - '\def\UrlBreaks{\do\/\do-\do\.\do\&\do\_\do?\do\#\do\=\do\%\do\~}'
 - '\makeatletter'
 - '\renewcommand{\section}{\@startsection{section}{1}{0pt}{2pt}{1pt}{\normalfont\Large\bfseries}}'
 - '\renewcommand{\subsection}{\@startsection{subsection}{2}{0pt}{1.5pt}{0.5pt}{\normalfont\large\bfseries}}'
 - '\makeatother'
---

# MAE 2250 — Semester Design Project

**Team:** _Big Red Stompers_
**Clients:** Cornell CALS Extension · E&J Gallo Winery · National Grape

Spotted lanternflies (SLF) are an invasive pest devastating Northeast vineyards, with each egg mass producing 30–60 nymphs that drive rapid population growth across seasons. Working with our clients, our team designed the **Stomp n' Scrape** — a handheld device that crushes SLF egg masses and scrapes the remains into an alcohol-filled vessel, giving the general public a fast, low-mess way to interrupt the lanternfly life cycle before adults emerge. This page documents three milestones from the semester.

## Milestones

1. [Client Pitch (O3)](#client-pitch) — Initial problem framing and concept proposal.
2. [Functional Prototype (O5)](#functional-prototype) — First working build and integration of subsystems.
3. [Client Report](#client-report) — Final prototype, testing results, and recommended next steps.

---

## Client Pitch {#client-pitch}

### Problem Statement
Spotted lanternflies (SLF) mainly target grapevines. As a result, grape farmers are trying to manage SLF populations in vineyards and nearby trees. SLF egg masses contain around 30-60 eggs, creating rapid population growth that affects later growing seasons. Current SLF population reduction methods, such as netting and manual egg removal, are difficult to scale across larger vineyards.

### Impact
Elimination of SLF eggs prevents the development of adult populations causing the most damage to vineyards. The average SLFs per vine starts low, increasing sharply following the transition from nymph to adult stages (Figure 1). As a result, attacking the root cause would protect regions like Lake Erie and the Finger Lakes from losses between &#36;1.5 million in year one and &#36;8.8 million by year three of infestation (Hayes).

### Proposed Concept: Stomp n' Scrape
**What it is:** Handheld egg removal device.

**How it would be used:** Designed to crush SLF egg mass shells and immediately scrape them into a rubbing-alcohol-filled vessel to prevent hatching.

**Why it's better than the status quo:**

- Reduces the chance of leaving viable eggs behind.
- Minimizes mess and user discomfort by sealing egg material instantly.
- Improved output and efficiency compared to manual scraping alone.

**End-of-semester proof-of-concept:** A functional prototype with a crushing feature, integrated scraper, and removable alcohol container, fabricated using 3D-printed components and accessible materials, and tested on simulated SLF egg masses to evaluate effectiveness and ease of cleaning.

### Key Risks / Unknowns

- **1** — Egg masses harden, making it difficult to ensure they are fully damaged. Two methods to kill the egg masses: crushing them and then scraping them into rubbing alcohol to kill the remaining ones.
- **2** — Public aversion to kill/interact with SLF, as crushing egg masses may be off-putting. Test with user trials and gauge user comfort.
- **3** — Many eggs are laid on high surfaces; 98% of eggs are found at unreachable heights (+10 feet) on trees (Krawczyk). Test attachments to extendable tools for users to reach higher egg masses.

### Questions for Client
1. **What is preventing you from currently targeting egg masses? Is it location, time or resources?**
   *Decision affected:* This would affect the aspects we want to emphasize in our design, like making it accessible to higher areas of the tree and ease to clean, based on client demand.
2. **Are there methods for reaching high areas that you are currently using?**
   *Decision affected:* This would affect whether our product must account for reaching high-up areas, or if it can be used with existing tools.
3. **How much would you need to reduce or eliminate SLF after they've already reached the grapevines?**
   *Decision affected:* This would affect our focus from egg masses, potentially shifting our direction to solving the problem of SLFs in their adulthood phase.

### References

- New York State Integrated Pest Management. (n.d.). *Spotted lanternfly management.* Cornell CALS College of Agriculture and Life Sciences. <https://cals.cornell.edu/integrated-pest-management/outreach-education/whats-bugging-you/spotted-lanternfly>

- Hayes, C. (2025, January 27). *Spotted lanternflies could cost NYS grape industry millions.* Cornell Chronicle. <https://news.cornell.edu/stories/2025/01/spotted-lanternflies-could-cost-nys-grape-industry-millions>

- Krawczyk, G. (2023, August 30). *What should you do with spotted lanternfly egg masses?* PennState Extension. <https://extension.psu.edu/what-should-you-do-with-spotted-lanternfly-egg-masses>

### Figure

![Average SLFs per Vine (2018-2020)]({{ "/assets/images/avg_slf_per_vine.png" | relative_url }}){: style="max-width:100%; width:450px; height:auto; display:block; margin:0 auto;"}

---

## Functional Prototype {#functional-prototype}

### Design Intent and Functionality
The functional prototype combines three operations into a single handheld device:

1. **Scraping** — the scraper removes the spotted lanternfly egg mass from the surface.
2. **Crushing / stomping** — a spring-loaded internal stomper compresses the egg mass material to destroy the eggs.
3. **Collection** — the lower opening funnels egg residue into an attached bottle for containment and later neutralization.

### Parts List and Fabrication

- **Housing** — 3D printed at RPL; contains the sliding rail, supports the scraper assembly, and connects to the bottle interface.
- **Stomper face** — 3D printed at RPL; translates along the internal rail and compresses the egg mass during actuation.
- **Compression spring** — initially tested using McMaster spring 8969T983; additional testing was performed with a workshop spring better matched to the intended hand-actuated displacement.
- **Knob / actuation interface** — 3D printed at RPL; pulled by the user to compress the spring.
- **Scraper** — 3D printed at RPL; removes egg masses from the surface and guides debris toward the bottle attachment.
- **Bottle thread connector** — 3D printed as part of the lower housing; interfaces with a standard plastic bottle for residue collection.

### Components and Assembly

![Components and functions illustration]({{ "/assets/images/fp_components_sketch.png" | relative_url }}){: style="max-width:100%; width:700px; height:auto; display:block; margin:1em auto;"}

![CAD view — full assembly and internal scraper assembly]({{ "/assets/images/fp_cad_views.png" | relative_url }}){: style="max-width:100%; width:700px; height:auto; display:block; margin:1em auto;"}

The prototype is assembled in the following order:

1. **Prepare the spring-and-rod subassembly.** Place the compression spring onto the rigid rod. The front circular plate and rigid rod are designed as a single 3D-printed part, so the spring seats directly onto this rod-and-plate subassembly.
2. **Prepare the shell casing.** Inspect the rear opening on the printed housing to confirm the spring-loaded subassembly can be inserted without interference.
3. **Insert the spring-loaded plate into the housing.** Slide the plate-with-spring subassembly into the shell casing through the rear opening so the spring and rod align with the internal axis of the housing.
4. **Attach the pull knob.** Screw the pull knob onto the exposed end of the rigid rod at the back of the housing. This creates the user-actuated interface for compressing the spring.
5. **Install the scraper.** Thread the scraper through the back opening of the housing and position it so it aligns with the front opening where the egg mass will be contacted.
6. **Attach the scraper plate to the rigid rod.** Secure the scraper plate to the rigid rod so motion of the rod-and-spring mechanism drives the scraper/stomping action.

### Design Tests

**Test 1 — Sliding Rail Motion and Interference.**
*Part tested:* housing rail and slider/stomper interface.
*What we measured:* whether the slider could move through its full range without excessive friction or jamming, since repeated manual actuation requires low-friction motion. Initiation force was measured with a spring scale attached to the slider, and all five team members rated ease of use from 1 (very easy) to 10 (very difficult).
*Result:* On first assembly the rail had excessive friction from insufficient CAD tolerance and print inaccuracy. Initiation force was 10 N and the mean difficulty score was 7/10. After sanding the rail surfaces, the mean score improved to 5/10,still outside our 1–4 usability target.
*Next iteration:* increase clearance between housing and slider by 5 mm, and switch from PLA to PETG to reduce print irregularities. Run repeated-cycle testing to confirm the rail doesn't bind over time.

**Test 2 — Spring Mechanism Force and Usability.**
*Part tested:* compression spring and stomping mechanism.
*What we measured:* whether the spring could be compressed by hand while still supplying enough force to help crush the egg mass. Target force from earlier work was roughly 50–70 N. We manually compressed the McMaster spring through the intended actuation path, then tested a workshop spring and estimated its spring constant using Hooke's Law from a 500 g load producing 1.5 in of displacement.
*Result:* The McMaster spring was too stiff; only a few millimeters of hand-compressed displacement, far below what the design needs. The workshop spring's constant came out to roughly 129 N/m (≈0.74 lbf/in), close to our rough target. Later trials suggested that confidently producing crushing force across a ~2 in (~50 mm) stroke would require a stiffer spring, in the 3–3.5 lbf/in range.
*Next iteration:* select a spring with a slightly higher spring constant than the workshop spring while remaining usable, and redesign the rod/attachment geometry to improve load transfer between spring and stomper.

### Success Criteria for the Final Prototype

| # | Criterion | Target | Priority |
|---|---|---|---|
| 1 | **Portability** | ≤ 0.5 kg; ≤ 20 cm without bottle, ≤ 30 cm with bottle | Lower |
| 2 | **Egg destruction effectiveness** | ≥ 95% of eggs destroyed in one actuation (measured with pea/Orbeez analogs) | High |
| 3 | **Removal speed** | < 10 s average per egg mass across 10 trials | Very high |
| 4 | **Residue capture** | ≥ 80% of removed residue funneled into the bottle | High |

### Exhibit-Day Demonstration
The exhibit-day demonstration focuses on the two criteria that produce visible, measurable outcomes: complete egg-mass removal in under 10 seconds, and at least 80% residue capture in the bottle. The team uses a substitute egg mass on a test surface, times the removal, and shows that most residue is visibly directed into the bottle attachment.

---

## Client Report {#client-report}

### Context and Problem
Spotted lanternflies (SLF) pose a growing threat to vineyards. Each egg mass contains 30–60 eggs, driving exponential population growth and peak crop damage as nymphs develop into adults (Chamberlin). Left unchecked, infestations could cost regions like Lake Erie and the Finger Lakes around $1.5 million in year one and up to $8.8 million by year three (Hayes), making the egg stage the most effective intervention point. Current methods like netting are difficult to scale, the eggs harden over time and become harder to remove, and the public is often discouraged from removing them because of how off-putting the process is. These constraints are why we designed a more effective, user-friendly egg removal solution.

### Final Prototype and Application
The Stomp n' Scrape is a handheld device that targets SLF egg masses. A stomper crushes the eggs and a scraper sweeps them into a sealed bottle. The product is compact, portable, cost-efficient, and easy to manufacture — built so a wide public audience, not just grape farmers, can help address SLF populations.

To assemble the device, the housing threads onto a plastic water bottle. The spring sits on the stomper's rod, which is threaded onto the knob. The scraper sits in the ring holder when the device is not in use. To crush eggs, the user pulls the knob back and releases it, repeating until the eggs are sufficiently crushed. The scraper is then inserted through the slits, allowing the user to clean the stomper face.

![Assembly diagram for the Stomp n' Scrape]({{ "/assets/images/assembly_diagram.png" | relative_url }}){: style="max-width:100%; width:700px; height:auto; display:block; margin:1em auto;"}

### Prototype and Testing Details
The prototype used in the following tests is the final 3D print the Big Red Stompers manufactured given the time constraints of the course. The print was made in PETG with the scraper attachment on the left side of the housing.

**Test 1 — Stomper Effectiveness.** We used mustard seeds as a stand-in for SLF eggs — a conservative model since they are harder to crush than real SLF eggs. We measured the percentage of seeds crushed after one to five stomps, with a benchmark of 99%+ at five stomps. This test was important to show the concept could produce effective results. *Result:* The stomping component is optimized to destroy egg masses within a reasonable number of stomps. Further testing on durability under repeated use is still needed.

![Seeds Crushed vs. Number of Stomps]({{ "/assets/images/seeds_crushed_vs_stomps.png" | relative_url }}){: style="max-width:100%; width:600px; height:auto; display:block; margin:1em auto;"}

**Test 2 — Time of One Use.** We timed one full stomp-and-scrape cycle: five sets of five stomps and one scrape at varying heights on a tree, using a chia/mustard seed mix to simulate egg masses, repeated three times. Ease of use is critical for a public consumer base. *Result:* All cycles satisfied the under-120-second target. Time-of-use can be further reduced by moving the scraper holder to the right-hand side of the casing for right-handed users, and adding a stopper at the end of the scraper so it auto-aligns with the device, reducing the positioning time before scraping.

![Trial Number and Use Time for One Cycle]({{ "/assets/images/cycle_time_per_trial.png" | relative_url }}){: style="max-width:100%; width:600px; height:auto; display:block; margin:1em auto;"}

**Test 3 — Scraper Effectiveness.** We covered the stomper with chia seeds at 100%, 75%, 50%, 25%, and 10% surface coverage, then recorded the percentage of surface area still covered after one scrape pass. This is relevant to how cleanly and reusably the device performs. *Result:* Most residue collected at the top edge and bottom corners of the stomper — outside the scraper's current range of motion. Lengthening the slots on both sides of the housing would extend the scraper's range and address these weak spots.

![Scraper Effectiveness: Surface Area vs. Percentage of Seeds Scraped]({{ "/assets/images/scraper_effectiveness.png" | relative_url }}){: style="max-width:100%; width:600px; height:auto; display:block; margin:1em auto;"}

### Conclusion and Recommendation
The overall mechanism works, but testing surfaced several areas for improvement. First, the scraper should be redesigned with longer side tracks to extend its range of motion, since Test 3 showed weak spots on the edges of the face the scraper currently cannot access. Second, the knob should be redesigned with a hook shape to give users a more secure grip, which would shorten time-of-use. Finally, future iterations should test different print materials and add durability testing to ensure the product is reusable and reliable.

Because the final prototype is inexpensive to manufacture, the Stomp n' Scrape has strong potential to scale for public use with minor design improvements. Since the target users are the general public rather than only grape farmers, marketing through TikTok, Instagram, and other social media platforms could help drive adoption. Outreach to environmental and agricultural entities with a vested interest in reducing SLF populations could further support distribution — those entities could sponsor and purchase the product for consumers who would use it if they could obtain it for free.
### Bill of Materials

| Item | Cost | Stage |
|---|---|---|
| Compression Spring #1 | $6.05 | Prototyping |
| 3D Print #1 (PLA) | $3.18 | Prototyping |
| 3D Print #2 (PETG) | $3.14 | Prototyping |
| Mustard Seeds | $5.99 | Testing |
| Chia Seeds | $8.98 | Testing |
| 3D Print #3 (PETG) | $3.14 | Prototyping |
| Compression Spring #2 | $4.60 | Final Prototype |
| 3D Print #4 (PETG) | $3.14 | Final Prototype |
| **Total project cost** | **$38.22** | |
| **Final prototype cost** | **$7.74** | |

### Final Component List
- 3D-printed shell, plate, knob, and scraper
- Compression spring (McMaster-Carr)

### References

- Chamberlin, L. (2022, February 23). *Spotted lanternfly egg mass scouting — DIY!* Virginia Department of Forestry. <https://dof.virginia.gov/spotted-lanternfly-egg-mass-scouting-diy/>
- Hayes, C. (2025, January 27). *Spotted lanternflies could cost NYS grape industry millions.* Cornell Chronicle. <https://news.cornell.edu/stories/2025/01/spotted-lanternflies-could-cost-nys-grape-industry-millions>
---
layout: project
title: Parallel vs. Counterflow Heat Exchanger Analysis
math: true
description: Portfolio Assignment ENGRD 2210
technologies: [LaTeX, AI to convert raw calculations into LaTeX format
https://www.engineeringtoolbox.com/arithmetic-logarithmic-mean-temperature-d_436.html, https://innovationspace.ansys.com/courses/wp-content/uploads/sites/5/2021/02/LT4C3-Lesson4-Handout-NT.pdf]
image: /assets/images/heatexchanger.png
---
In Homework 11 for ENGRD 2210, we were asked to select a real device from the course and analyze how its performance changes under different operating conditions. I chose a liquid–liquid heat exchanger, similar to the one used in our lab section, and focused on how **flow arrangement** (parallel vs. counterflow) and **pump flow rate** affect heat transfer and outlet temperatures.

The working fluids are water streams on both sides, so I take a constant specific heat
$c_p \approx 4.18\,\text{kJ/(kg·K)}$ for both the hot and cold sides.


---

## 1. Device Description and Measured Temperatures

The heat exchanger consists of two separate water circuits:

- **Hot side (H):** water entering at an elevated temperature.
- **Cold side (C):** water entering near room / chilled-water temperature.

Representative tank temperatures for the **reservoirs** feeding the exchanger were

- Initial hot reservoir temperature:  
  $$T_{H,\text{tank, initial}} \approx 40^\circ\text{C}$$
- Initial cold reservoir temperature:  
  $$T_{C,\text{tank, initial}} \approx 6.6^\circ\text{C}$$

After operating the system, the mixed reservoir temperatures approached

- $$T_{H,\text{tank, final}} \approx 18.6^\circ\text{C}, \qquad
   T_{C,\text{tank, final}} \approx 23.3^\circ\text{C}$$

which already suggests a significant net heat transfer from the hot loop to the cold loop.

Along the heat exchanger itself we recorded representative **inlet/outlet** temperatures
for three cases:

1. **Parallel-flow, lower pump flow rate**
   - Cold side:  
     $$T_{C,\text{in}} \approx 11.3^\circ\text{C}, \quad
       T_{C,\text{out}} \approx 26.3^\circ\text{C}$$
   - Hot side:  
     $$T_{H,\text{in}} \approx 35.0^\circ\text{C}, \quad
       T_{H,\text{out}} \approx 22.3^\circ\text{C}$$

2. **Parallel-flow, higher pump flow rate**
   - Cold side:  
     $$T_{C,\text{in}} \approx 10.0^\circ\text{C}, \quad
       T_{C,\text{out}} \approx 22.3^\circ\text{C}$$
   - Hot side:  
     $$T_{H,\text{in}} \approx 35.5^\circ\text{C}, \quad
       T_{H,\text{out}} \approx 24.7^\circ\text{C}$$

3. **Counterflow, similar flow rate**
   - Cold side:  
     $$T_{C,\text{in}} \approx 11.0^\circ\text{C}, \quad
       T_{C,\text{out}} \approx 24.6^\circ\text{C}$$
   - Hot side:  
     $$T_{H,\text{in}} \approx 35.5^\circ\text{C}, \quad
       T_{H,\text{out}} \approx 21.3^\circ\text{C}$$

These data sets let me compare how flow arrangement and pump setting influence
the temperature approach and overall heat-transfer driving force.

---

## 2. System Diagram and Control Volume

I treat the **heat exchanger itself** as a steady-flow control volume. Each stream is a separate flow path that exchanges energy only by heat within the exchanger walls—there is no direct mixing of the two fluids.

- **Mass flow rates:**
  - Hot side: $\dot m_H$
  - Cold side: $\dot m_C$

- **Energy interaction:**
  - A heat rate $\dot Q$ is transferred *from* the hot stream *to* the cold stream.
  - Shaft work is negligible ($\dot W \approx 0$); the pump and any fan power are outside my control volume.

Conceptually, the diagram has:

- An inlet and outlet on the hot side: $(\dot m_H,\, T_{H,\text{in}})$ and $(\dot m_H,\, T_{H,\text{out}})$.
- An inlet and outlet on the cold side: $(\dot m_C,\, T_{C,\text{in}})$ and $(\dot m_C,\, T_{C,\text{out}})$.
- A heat flux crossing the common wall, directed from hot to cold.

---

## 3. Governing Equations

### 3.1 Mass Balances

For each side, at steady state with a single inlet and outlet,

$$
\dot{m}_{H,in} = \dot{m}_{H,out} = \dot{m}_H,
$$

$$
\dot{m}_{C,in} = \dot{m}_{C,out} = \dot{m}_C.
$$

There is no mass exchange between the two circuits.

### 3.2 Energy Balance

Neglecting kinetic and potential energy changes, and taking the control volume as just the exchanger shell and tubes,

$$
\dot{Q} + \dot{m}_H h_{H,in} + \dot{m}_C h_{C,in}
= \dot{m}_H h_{H,out} + \dot{m}_C h_{C,out}.
$$

For nearly incompressible liquids with constant specific heat \(c_p\),

$$
h \approx c_p T,
$$

so

$$
\dot{Q} = \dot{m}_C c_p \left( T_{C,out} - T_{C,in} \right),
$$

$$
\dot{Q} = \dot{m}_H c_p \left( T_{H,in} - T_{H,out} \right).
$$

From the temperature data we can compare the temperature rises and drops to infer the ratio of flow rates:

$$
\frac{\dot{m}_C}{\dot{m}_H}
\approx
\frac{T_{H,in} - T_{H,out}}{T_{C,out} - T_{C,in}}.
$$

### 3.3 Entropy Balance and Irreversibility

Treating the environment at a uniform temperature \(T_0\), the entropy balance
for the exchanger is

$$
\dot{S}_{gen} =
\dot{m}_H (s_{H,out} - s_{H,in})
+ \dot{m}_C (s_{C,out} - s_{C,in})
- \frac{\dot{Q}}{T_0}.
$$

With constant \(c_p\) and small pressure changes we can approximate

$$
s_{out} - s_{in} \approx c_p \ln\!\left(\frac{T_{out}}{T_{in}}\right),
$$

and we would find \(\dot{S}_{gen} > 0\) in every case, consistent with the
Second Law. The entropy generation is lower when the temperature difference
between the two streams is more uniform (as in counterflow).

--

## 4. Effect of Design and Operating Changes

The two main “knobs” I considered are:

- Flow arrangement: parallel vs. counterflow  
- Pump flow rate (low vs. high)

### 4.1 Parallel vs. Counterflow – Temperature Driving Force

A key performance metric for a heat exchanger is the log-mean temperature difference (LMTD), which measures the effective driving force for heat transfer.

For **parallel flow**:

$$
\Delta T_1 = T_{H,in} - T_{C,in}, \qquad
\Delta T_2 = T_{H,out} - T_{C,out},
$$

$$
\Delta T_{\text{lm,parallel}} =
\frac{\Delta T_1 - \Delta T_2}
     {\ln\!\left(\dfrac{\Delta T_1}{\Delta T_2}\right)}.
$$

For **counterflow**:

$$
\Delta T_1 = T_{H,in} - T_{C,out}, \qquad
\Delta T_2 = T_{H,out} - T_{C,in},
$$

$$
\Delta T_{\text{lm,counter}} =
\frac{\Delta T_1 - \Delta T_2}
     {\ln\!\left(\dfrac{\Delta T_1}{\Delta T_2}\right)}.
$$

Using the high-flow parallel and counterflow data:

- Parallel (high flow):
  $$
  \Delta T_1 \approx 35.5 - 10.0 = 25.5^\circ\mathrm{C}, \qquad
  \Delta T_2 \approx 24.7 - 22.3 = 2.4^\circ\mathrm{C}.
  $$

- Counterflow:
  $$
  \Delta T_1 \approx 35.5 - 24.6 = 10.9^\circ\mathrm{C}, \qquad
  \Delta T_2 \approx 21.3 - 11.0 = 10.3^\circ\mathrm{C}.
  $$

The parallel case has one large and one very small temperature difference, so the LMTD is limited by the tiny outlet approach. In contrast, the counterflow case keeps the temperature difference more uniform along the length of the exchanger, resulting in a larger effective LMTD and therefore, for the same area and overall heat-transfer coefficient, a higher heat rate $\dot{Q}$.

Qualitatively, the measurements confirm the textbook result:

- **Parallel flow:** large driving force at the inlet, very small at the outlet.  
- **Counterflow:** more even driving force, better use of the entire surface area, and the cold stream can exit at a temperature closer to the hot inlet.


### 4.2 Effect of Pump Flow Rate

Comparing the parallel low-flow and parallel high-flow cases:

- At **lower flow rate**, each fluid experiences a larger temperature change (more residence time in the exchanger).  
- At **higher flow rate**, the temperature changes per pass are smaller, but the mass flow rate and thus the total heat rate
  $$
  \dot{Q} = \dot{m}\,c_p\,\Delta T
  $$
  can still increase because $\dot{m}$ increases even as $\Delta T$ shrinks.

From the data:

- Low-flow parallel:
  $$
  \Delta T_H \approx 35.0 - 22.3 = 12.7^\circ\mathrm{C}, \qquad
  \Delta T_C \approx 26.3 - 11.3 = 15.0^\circ\mathrm{C}.
  $$

- High-flow parallel:
  $$
  \Delta T_H \approx 35.5 - 24.7 = 10.8^\circ\mathrm{C}, \qquad
  \Delta T_C \approx 22.3 - 10.0 = 12.3^\circ\mathrm{C}.
  $$

The temperature changes get smaller, but if $\dot{m}$ increases enough, the overall heating and cooling capacity of the exchanger goes up. The tradeoff is the extra pump power required to deliver that higher flow rate.


---

## 5. Design Change and Performance Impact

A realistic design change based on this analysis is:

> **Switch from a parallel-flow to a counterflow arrangement while choosing flow rates to match capacity rates on both sides.**

With the measured counterflow case:

- The hot outlet temperature drops lower than in parallel flow for similar inlet conditions, indicating better energy extraction from the hot stream.
- The cold outlet temperature rises to nearly match the hot inlet temperature range, which is ideal if the goal is to heat the cold stream as much as possible.

From a design standpoint:

For a fixed heat-transfer area \(A\) and overall heat-transfer coefficient \(h\), the heat rate is

$$
\dot{Q} = h\,A\,\Delta T_{\mathrm{lm}}.
$$

Increasing $\Delta T_{\mathrm{lm}}$ via counterflow is effectively “free performance” compared to enlarging $A$.

Matching the capacity rates $\dot m_H c_{p,H} \approx \dot m_C c_{p,C}$ on both sides (as suggested by our counterflow data) maximizes the effectiveness of the heat exchanger.






In practice, I would recommend:

1. **Counterflow arrangement**, to maximize the log-mean temperature difference and minimize entropy generation.
2. **Flow rates chosen so that** $\dot m_H c_{p,H} \approx \dot m_C c_{p,C}$, which balances the temperature changes on both sides and pushes the outlet temperatures closer together.
3. **Fine-tuning pump speed** to trade off between slightly smaller $\Delta T$ and higher $\dot m$ and capacity, depending on whether the design is constrained more by available heat-transfer area or by pumping power.

Overall, the measurements show that the counterflow configuration with carefully chosen flow rates uses the exchanger area more efficiently, increases the useful heat transfer between the hot and cold streams, and better aligns with the thermodynamic ideal of lower entropy generation for the same duty.












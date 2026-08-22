---
permalink: /research/
author_profile: true
---

Introduction
======
In nuclear fuel recycling plants, Gamma ($\gamma$) absorptiometry is used on acidic solutions to quantify Uranium and Plutonium levels in real-time as a safety measure. 
These measurements allow for reliable readings with around 10% uncertainty, but rely on aging (if not obsolete) hardware.

The purpose of this research work is to prove that an alternative technique called *Laser-Induced Breakdown Spectroscopy* (LIBS) can be employed to achieve sub-10% uncertainty for U, Pu, and other elemental concentrations in acidic solutions.
Although LIBS has proven its worth as a robust in-situ elemental analysis technique on planetary missions (e.g., Curiosity in 2011 and Perseverance in 2020), active research continues to advance the field and overcome analytical limitations. 

This work falls within the domain of "chemometrics," a field bridging data-driven approaches and chemistry. 
This project focuses on advanced machine learning methods beyond conventional chemometrics (e.g., simple calibration curves, PCA), developed through a collaboration between a physics/chemistry laboratory (LANIE) and an AI-focused laboratory (LIAD).

Objectives
======
Applying AI methods to LIBS in order to:
- Optimise experimental parameters such as laser power, gate delay, and gate width.
- Develop elemental quantification techniques for actinide (U/Pu) surrogates, specifically lanthanides (Nd, Ce, Gd), within acidic or aqueous solutions.
- Provide uncertainty quantification (UQ) while keeping said uncertainty in the single digits (<10%).

Challenges
======
The abundance of tuneable experimental parameters and the non-linearity of their respective influences make signal optimisation non-trivial.
Key experimental variables include:
- Spectrometer type (Czerny-Turner, Échelle)
- Laser wavelength (UV/Visible/IR) and pulse power
- Focal point positioning (depth in the jet and horizontal offset)
- Shielding gas selection (e.g., Argon, Helium)
- Camera parameters (gain, gate width/delay, readout speeds)

Defining a "better LIBS signal" is also ambiguous, as objective criteria may differ between applications:
- Highest Signal-to-Noise Ratio (SNR)
- Lowest Limit-of-Detection (LoD)
- Highest Signal-to-Background Ratio (SBR)
- Maximum reproducibility, evaluated by:
  - Low Relative Standard Deviation (RSD) of peak areas across replicates
  - Lower variance across the entire spectrum over multiple replicates

While LIBS spectrum inversion can be straightforward for light elements with sparse emission lines, actinides and lanthanides produce highly complex spectra with thousands of *overlapping and interfering emission lines*. 
This challenge is compounded by severe concentration imbalances (e.g., 100 g/L Nd, 8.5 g/L Ce, and only 0.25 g/L Gd), which enhances matrix effects.

Finally, two distinct levels of uncertainty must be estimated and optimized:
- **Measurement uncertainty:** Natural signal fluctuations driven by specific experimental parameters and external factors.
- **Quantification uncertainty:** Predictive probability and accuracy associated with modeled elemental concentrations.

Laboratories
======
**LANIE** _Laboratory for Nuclear, Isotopic and Elemental Analytical Development_<br>
Under the supervision of [Jean-Baptiste SIRVEN](https://www.researchgate.net/scientific-contributions/Jean-Baptiste-Sirven-2014420753)

**LIAD** _Laboratory for AI & Data Science_<br>
Under the supervision of [Riccardo FINOTELLO](https://scholar.google.com/citations?user=mT3o06QAAAAJ&hl=it)
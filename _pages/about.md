---
permalink: /
title: "Description"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

Computer science engineer specialising in Big Data. 
I finished high school and completed my Master’s degree early (at age 21), graduating at the top of my cohort (1st out of 196). 
Currently enrolled in a PhD programme at the CEA, affiliated with Université Paris‑Saclay.

Laboratories
======
**LANIE** _Laboratory for Nuclear, Isotopic and Elemental Analytical Development_

Under the supervision of [Jean-Baptiste SIRVEN](https://www.researchgate.net/scientific-contributions/Jean-Baptiste-Sirven-2014420753)

**LIAD** _Laboratory for AI & Data Science_

Under the supervision of [Riccardo FINOTELLO](https://scholar.google.com/citations?user=mT3o06QAAAAJ&hl=it)

PhD Project
======
Applying multivariate techniques to liquid-based Laser-Induced Breakdown Spectroscopy (LIBS) to:
- Optimise experimental parameters such as laser power, gate delay, and gate width.
- Develop elemental quantification techniques for actinides (U/Pu) and lanthanides (Nd/Ce/Gd) within acidic or aqueous solutions.
- Provide uncertainty quantification (UQ) and keep said uncertainty in the order of single digits (<10%).

While LIBS has been widely adopted as an alternative to XRF or Gamma ($\gamma$) absorptiometry techniques for in-situ elemental analysis in recent years (e.g., Curiosity in 2011 and Perseverance in 2020), liquid LIBS is still a relatively new domain where research is expected to thrive in the near future. 

This work falls within the domain of "chemometrics," a field that bridges data-driven approaches and chemistry. This project will focus on techniques more sophisticated than standard chemometrics (e.g., calibration curves, PCA), as it is a collaboration between a physics/chemistry lab (LANIE) and an AI-centred lab (LIAD).

The abundance of tunable parameters in the experiment makes it difficult to pinpoint which parameters to steer toward to achieve a better signal. The definition of a "better signal" can be ambiguous, as it could imply:
- Highest reproducibility:
  - Constant area under a peak?
  - Lower variance across the entire spectrum?
  - Should normalisation be applied before optimising?
- Highest Signal-to-Noise Ratio (SNR)
- Highest emission line-to-background ratio

Furthermore, the goal of this PhD is to obtain a "plug-and-play" solution without a calibration step, known as calibration-free LIBS (CF-LIBS), where a model (univariate or multivariate) predicts the concentration of multiple elements. While this can be straightforward for light elements with few emission lines, actinides and lanthanides are well known for producing highly complex spectra with thousands of interfering emission lines. This challenge is exacerbated when concentrations are unbalanced (i.e., one element is significantly more concentrated than others), which is the case here: 100 g/L of Nd, 8.5 g/L of Ce, and only 0.25 g/L of Gd.

Finally, multiple uncertainties must be estimated or modelled (and optimised):
- The measurement uncertainty (i.e., how likely the signal is to naturally fluctuate with specific experimental parameters).
- The elemental concentration quantification uncertainty (i.e., the probability that the predicted elemental concentration is accurate).
This can be achieved through intrinsic (e.g., probabilistic models) or extrinsic methods (e.g., ensemble methods), adding another layer of complexity to the project.
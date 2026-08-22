---
title: 'Spectratom 2026'
date: 2026-05-22
permalink: /posts/2026/spectratom-2026
tags:
  - conference
  - poster
  - abstract
---

I had the great pleasure of presenting a poster at the Spectratom 2026 conference held in Pau, France.
Here, I presented [preliminary work]({{ '/files/Spectratom2026.pdf' | relative_url }}) on experimental LIBS parameter optimization and validation.

Spectratom is an international conference dedicated to atomic spectroscopy research.
It mostly features ICP-type techniques (ICP-MS, ICP-OES, etc.) capable of parts-per-billion (ppb) detection limits.
While LIBS cannot offer ppb-level LoDs, it has the key advantage of requiring no extensive sample preparation.

As complex as LIBS is, obtaining *a signal* is relatively straightforward: if the laser energy is sufficient to generate a plasma, and the gate delay is short enough to capture photons during its lifetime, you will almost certainly get a spectrum.

The difficult part of LIBS, especially liquid-based LIBS, is obtaining *the optimal signal*.
Similar to the approach by *Sato et al.* in their [2023 paper](https://pubs.rsc.org/ja/article-abstract/38/11/2458/811291/Bayesian-optimization-of-the-conditions-for-highly?redirectedFrom=fulltext), we presented a framework using surrogate modeling via Gaussian Processes (GPs) and Bayesian optimization (BO) to efficiently steer experimental parameters toward the global optimum.

In their paper, they successfully lowered the LoD of silicone oil on aluminum surfaces by optimizing 3 parameters (pulse energy, stage height, and detection height).

Our goal was to adapt and expand their methodology to a higher-dimensional space, accounting for 10 experimental parameters while aiming to minimize the Relative Standard Deviation (RSD) of a Cerium emission line (418.66 nm):
- Laser pulse energy, laser horizontal offset relative to the stream
- Shot count, accumulation count
- Camera gain, gate delay, gate width, preamplifier gain
- Liquid jet flow rate, shielding gas flow rate

The rationale for minimizing RSD on the Cerium line is clear: we are working with an imbalanced matrix (100 g/L Neodymium vs. 8.5 g/L Cerium). 
The minor Cerium line exhibits higher RSD overall, so we prioritize obtaining the cleanest and most reproducible signal possible, a "help the weak signal first" strategy.

As mentioned earlier, since obtaining *a signal* is easy, classifying parameter spaces that won't produce one is equally manageable. Hence, we transitioned from standard BO to Constrained Bayesian Optimization (cBO), employing a classifier GP that learns the "feasibility region" by explicitly excluding the no-signal and saturation zones.

While LoD is relatively straightforward to model because it tracks Signal-to-Noise Ratio (SNR) ($$\mu / \sigma_{\text{background}}$$), which scales directly with laser energy until detector saturation, RSD is defined as ($$\sigma_{\text{replicates}} / \mu$$), making it inherently more volatile and non-linear. Moreover, external experimental fluctuations often compete directly with parameter influence. 

In short, the BO's objective was to minimize RSD (improve repeatability), enhance SNR (improve quality) while following constraints on feasability.

As reaching a 0% RSD is impossible due to external environmental noise, our goal was twofold: either successfully reduce RSD (or keep it steady while increasing SNR), or demonstrate that a small Latin Hypercube Sample (LHS) can quickly find an RSD regime bounded only by external noise.

With this Constrained BO approach, we achieved a stable 1.5–2% RSD regime for the Cerium line (compared to an LHS median of ~6%) while significantly improving SNR ($$\approx \times 2$$).

**Limitations:**
Net signal intensity was initially calculated by subtracting a background intensity value sampled from an emission-free spectral region. 
However, at extremely short gate delays (<150 ns), the baseline (bremsstrahlung radiation) exhibited an asymmetric spectral tilt (lower intensity at short wavelengths, higher at long wavelengths). Because our Cerium line was located on the far right of the spectral window while the background sample was taken from the far left, this calculation introduced a systematic bias in our net signal (and thus RSD) calculation.

In future steps, full baseline subtraction algorithms will be used instead of single-region background subtraction. While this limitation does not invalidate the Bayesian optimization methodology (the BO successfully found an optimum relative to the defined objective function), it highlighted that modeling RSD became noticeably harder once this baseline artifact was corrected. 

$$\rightarrow$$ *I have been working on this, so stay tuned!*

## Poster

<iframe
  src="{{ '/files/Spectratom2026.pdf' | relative_url }}"
  width="100%"
  height="800"
  style="border: 1px solid #ddd;">
</iframe>

<p>
  <a href="{{ '/files/Spectratom2026.pdf' | relative_url }}" target="_blank" rel="noopener">
    Open the PDF in a new tab
  </a>
</p>

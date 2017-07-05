---
author: remy
comments: false
date: 2011-03-15 11:44:22+00:00
layout: post
published: true
slug: piano-body-deconvolution
title: Piano body deconvolution
wordpress_id: 113
categories:
- science
---

This is a simple experiment with blind piano body deconvolution using log-spectrum averaging of the whole sound FFT (>37s) for all sounds in a piano database.

- Here is the minimum phase IR extracted from all the highest velocities piano samples: [piano body V5]({{ site.url }}/sounds/piano_body/piano_body_V5.wav)
- The minimum phase IR extracted from all the non sustained piano samples with highest velocity: [piano body nosus v5]({{ site.url }}/sounds/piano_body/piano_body_nosus_v5.wav)
- The minimum phase IR extracted from all the release piano samples: [piano body Rls]({{ site.url }}/sounds/piano_body/piano_body_Rls.wav)
- The minimum phase IR extracted from all the C3 samples: [piano body C3]({{ site.url }}/sounds/piano_body/piano_body_C3.wav)
- And the C3-v4 excitation deconvolved by piano_body_C3: [German v4 C3 deconv]({{ site.url }}/sounds/piano_body/German-v4-C3.wav_deconv.wav)

The extracted sounds obviously inherit the average EQ of the given sample set. But the results are not so bad given the simple means used.

### References:

- A. Openheim, R.W Schafer, T. G. Stockham ["Nonlinear Filtering of Multiplied and Convoled Signals"](http://www.rle.mit.edu/dspg/documents/nonnlinearfiltering_1968.pdf)
- Mohamed Tria, Mirko Van Der Baan, Anthony Larue, Jerome Mars, ["Wavelet estimation in homomorphic domain by spectral averaging, for deconvolution of seismic data"](http://hal.archives-ouvertes.fr/docs/00/13/81/70/PDF/PSIP2007_fulpap.pdf)

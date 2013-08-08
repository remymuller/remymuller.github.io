---
author: remy
comments: false
date: 2010-12-16 14:52:37+00:00
layout: page
slug: blind-demixing-using-non-negative-matrix-factorization
title: Blind demixing using Non-negative Matrix Factorization
wordpress_id: 41
categories:
- Science
---

![]({{ site.url }}/images/AFXdemixS.png)


This is a commandline program that lets you decompose a sound into additive components in the spectral domain.


## what it does

1. generate the sound's spectrogram	
1. decompose the spectrogram into N layers
1. resynthesize each layer and the residual to a separate soundfile


usage:

    nmfdemix  [-m] [-s] [-o long] [-c double] [-i long] [-f long] [--] [-v] [-h] filename #components
    -o , --overlap _overlap factor (default 4)_
    -c , --criteria _stopping criteria (default 0.001)_
    -i , --maxiterations _max number of iterations (default 1000)_
    -f , --fftsize _fftsize (default 4096)_
    -m,  --matrixout _output W and H matrices_
    -s,  --silent _don't be verbose_


## download


[nmfdemix 0.11 for windows XP](http://recherche.ircam.fr/equipes/temps-reel/movement/muller/soft/nmfdemix-setup.exe)

[nmfdemix 0.11 for mac OSX](http://recherche.ircam.fr/equipes/temps-reel/movement/muller/soft/nmfdemix.dmg)

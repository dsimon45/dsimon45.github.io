---
layout: page
title: LSF Correction
description: Match the wavelength dependent line spread function of a template spectrum to a target spectrum with this code
img: assets/img/projects/lsf.png
importance: 1
category: work
---

# Why Care about Line Spread Functions?
Spectrographs don't return a perfect picture of a galaxy's spectrum. There is noise, from the sky, source, and detector. And then there is the line spread function (also called the spectral point spread function). The line spread function is a measure of how single spectral lines are broadened, not due to the source itself being broad, but due to the instrument. This artificial broadening must be taken account of when doing things like measuring kinematics since broadening from the LSF can look like kinematic broadening. 

The standard assumption in most spectral fitting pipelines is that the shape of the LSF is a Gaussian. In this case, you can match the LSF of a template to the LSF of a source by convolving the template with a gaussian with
\begin{equation}
\sigma = \sqrt{\sigma_{\rm LSF,source}^2 - \sigma_{\rm LSF,template}^2}
\end{equation}
In reality, however, the shape of the LSF often isn't Gaussian. A wide variety of LSF shapes have been observed, from profiles with broad wings to profiles that more closely resemble a top hat. 

# The Solution
In this paper I devised an algorithm for matching the LSF of a template to a source when the shape is not a Gaussian. Some example code showing how this is done is available [here](https://github.com/dsimon45/LSF_Matching/). Assuming you know the shape of the LSF for the template and source spectra, you can match the template to the source, meaning that any residual broadening measured is due purely to the kinematics, not to the LSF.



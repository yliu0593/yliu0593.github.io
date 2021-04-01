---
title: "General Adversarial Linear Discriminant Analysis"
collection: projects
type: "Projects"
permalink: /projects/galda
---

<!-- ![Cover Photo](/images/galda-concept.png){width="6in"} -->
<img src="/images/galda-concept.png" alt="Cover Photo" style="width:400px;"/>


## Motivation

- In spectral analysis, spectral data are often considered high-dimensional when the number of wavelength channels is on the order of thousands. 
- However, meaningful features exist on only a few of these channels.
- For example, the figure below shows the Raman spectra of clopidogrel where classes 1, 2 and 3 denote polymorph I, polymorph II, and background respectively.


<!-- ![Raman spec of Clopidogrel](/images/galda-raman.jpg){width="6in"} -->
<img src="/images/galda-raman.jpg" alt="ORaman spec of Clopidogrel" style="width:400px;"/>


- When analyzing high-dimensional data, they are prone to be overfitted when using traditional LDA. As shown on the left:  the training data (open dots) don’t represent the distribution of the testing data (solid dots).

<!-- ![Overfit in spectroscopic data](/images/galda-overfit.png){width="500px"} -->
<img src="/images/galda-overfit.png" alt="Overfit in spectroscopic data" style="width:400px;"/>

- In GALDA, we solve this “prone to overfitting” problem by using an algorithm structure analogous to a GAN (generative artificial neural network). We confirmed that the “resolution” produced by GALDA is better than that of PCA or PLS-DA.

# Methods

- GALDA is an iterative algorithm that follows an “attack-improve-attack- improve” loop process
- The “improve” step was done by doing a four class LDA – instead of three – to force the perturbed spectra to be classified as a fourth class.


<!-- ![Concept of GALDA](/images/galda-concept.png){width="500px"} -->
<img src="/images/galda-concept.png" alt="Concept of GALDA" style="width:400px;"/>


a) Raw data from three different classes

a) → b) performs traditional three-class LDA

b) → c) generates random noisy meaningless spectra

c) → d) calculates masks for the generated spectra such that they classify as targeted classes

d) → e) performs four-class LDA

e) → c) generates next generation of random noisy meaningless spectra

# Results

- Fischer’s discriminant J was used as a metric for quantifying resolution. It measures how well data points are separated in the reduced dimension.
- Left figure shows how the resolution changes during the GALDA iterative process, which is related to “reduce over-fitting”.


<!-- ![resolution](/images/galda-resolution.png){width="500px"} -->

<img src="/images/galda-resolution.png" alt="resolution" style="width:400px;"/>





We compared resolution of the reduced data, analyzed by GALDA, PCA, PLS-DA respectively. In the figure above, GALDA yields better resolution in comparison to the other two routinely used methods, especially significantly better than PLS-DA results.


<!-- ![comparison](/images/galda-comp.jpg) -->

<img src="/images/galda-comp.jpg" alt="comparison" style="width:400px;"/>


code are available at [Purdue Github](https://github.itap.purdue.edu/Simpson-Laboratory-for-Nonlinear-Optics/GALDA-public
)
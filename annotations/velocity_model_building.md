# Papers About Velocity Model Building (VMB) And Its Summaries

## Surveys

### 2019 - Yang, Fangshu, Ma, Jianwei, [Deep-learning inversion: a next generation seismic velocity-model building method](https://library.seg.org/doi/full/10.1190/geo2018-0249.1)

---

### 2021 - A. Adler, M. Araya-Polo and T. Poggio, [Deep Learning for Seismic Inverse Problems: Toward the Acceleration of Geophysical Analysis Workflows](https://ieeexplore.ieee.org/abstract/document/9363496)


#### Seismic inverse problems
"*Seismic inverse problems can be divided into two main categories: 1) **estimating an Earth model from recorded seismic
data**, also known as seismic inversion, **which is the main focus
of this article**, and 2) seismic signal restoration and enhancement, such as denoising, imputation, and bandwidth expansion, which are typically performed in a preliminary stage
previous to further seismic inversion and other geophysical analyses.*"

Focus on the problems:
- tomography,
- FWI,
- MS-FWI (Multiscale FWI),
- Reflectivity and impedance model building.

#### DL Solutions Classification

|DL FOR FWI PERFORMANCE ENHANCEMENT|
|-------|
|Regularizing FWI using probability map of salt bodies |
  

|END-TO-END SEISMIC INVERSION DLI|
|-------|
|MLP-based architectures|
|Semblance as input for CNN-based architectures|
|Seismic data as input for CNN-based architectures|
|Encoder–decoder architectures|
|Recurrent DL architectures|

|ADVANCED DL ARCHITECTURES|
|-------|
|Deep generative modeling|
|Physics-guided architectures|

---
### 2023 - Farbod Khosro Anjom, Francesco Vaccarino, and Laura Valentina Socco, [Machine learning for seismic exploration: Where are we and how far are we from the holy grail?](https://library.seg.org/doi/10.1190/geo2023-0129.1)

#### Interesting thinking
"*... is the goal of science to understand or predict? Alkhalifah (2022) believes, that
in the age of data science, we are moving back to predictive models
that can resolve many limitations of the physical models. He defines
ML as 'a very extensive numerical tool, nothing more and nothing
less, which is based on optimization.'*"

#### Motivation for DL Solutions
The main driver for moving to fully data-driven methods is the
idea of mitigating some drawbacks of the current technologies and
methods.

1. **Efficiency**: traditional methods relies in complex workflows which are based on analysis, tests and evalutions carried out with a trial and error approach and demands time and expertise. It would be very atrractive to have alternatives to directly provide results on a computer-based process whithout the need to make decisions.
   
1. **Bias**: the decisions made during complex workflows lead to uncontrolled bias and results are dificult to reproduce. ML-based solutions  may allow to obtain more repeatable and objective results.

1. **Effectiveness**: every processing and interpretation technique has intrinsic limitations and, according to the method and choices, the results
will allow us to “see” different things. The objective here is to have methods that automatically provide high-quality results, reflecting
rich information about the subsurface.

#### DL for Seismic's Challenges
"*We look at these new developments as a potential holy grail of
seismic exploration where the raw data are given to a machine that
provides automatically the best and most informative model in an efficient manner. 
This idea undoubtedly represents a revolution in the
way we carry out seismic processing and interpretation, but many
issues related to ML implementation must be addressed*"


|Challenges|
|-----|
| The complexity in the relationship between the model and the data in seismic exploration is incomparable to most of the problems that are now routinely solved by ML techniques. For example, the wave propagation inside the earth is much more complex than the wave propagation inside human organs that is used for medical imaging|
|*Transfer learning from other areas are dificult, actualy completely useless most of time*|
| Recquires lots of labeled data, which are scarse for real datasets |
|*Synthetic data often miss important characteristics from real noisy field data*|


#### Where are we on our path to search for the holy grail?







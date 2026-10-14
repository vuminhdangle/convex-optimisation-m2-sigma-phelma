# Convex Optimisation - M2 SIGMA (2025 - 2026)

Python and Jupyter Notebook implementations of convex optimisation methods, illustrated through three practical applications. 

Author: Vu Minh Dang LE

Programme: Master 2 Signal and Image Processing (SIGMA). 

School: Grenoble INP - Phelma. 

Academic year: 2025 - 2026. 

Course grade: 17/20.

## Overview

This repository documents my work for the *Convex Optimisation* course in the M2 SIGMA programme. The course introduces mathematical optimisation, with pratical examples and applications to inverse problem. Lectures are complemented by hands-on lab sessions, in which mathematical formulations are translated into numerical algorithms and evaluated experimentally. 

The three labs progress from constrained quadratic optimisation to support vector machines and sparsity-based image reconstruction. Each lab folder contains a Jupyter Notebook and a dataset. This repository includes the slide from my final oral examination, which focused on the third lab. 

## Lab sessions

| Lab | Topic | Main methods |
|-----|-------|--------------|
| 01 | Portfolio optimisation | Minimum-variance portfolios, Lagrange multipliers, simplex projection, projected gradient descent, log-barrier method |
| 02 | Support vector machines | Hard-margin SVM duality, projection methods, forward–backward splitting, proximal hinge loss, augmented Lagrangian |
| 03 | Compressive sensing and image denoising | Fourier sparsity, complex soft-thresholding, projection onto measurement constraints, Douglas–Rachford splitting, greedy/OMP baseline |

## Lab 01 - Portfolio optimisation

The objective is to construct a portfolio with low emperical risk using historical stock-market returns. The notebook studies the SP100 dataset, estimates an asset-return covariance matrix from training observations, and evaluates portfolios on the final 30 days. 

The experiments compare equal weighting with a budget-constrained minimum-variance portfolio (short selling allowed), a long-only portfolio obtained using projected gradient descent on the probability simplex, and an interior solution computed using a log-barrier formulation. The discussion examines the effect of constraints and the limitations of the barrier implementation and its parameter choices.

## Lab 02 - Support vector machines

This lab formulates binary classification as an optimisation problem and investigates both *hard-margin* and *soft-margin* SVMs.

The hard-margin part uses a dual formulation and projected forward–backward iterations to learn a separating hyperplane on a linearly separable synthetic dataset. The soft-margin part introduces the *hinge-loss proximal operator*, explores optimisation and convergence, and tests classification after a two-dimensional *PCA projection of MNIST digits* (including comparisons of digits 1 vs 7 and 4 vs 9). An augmented-Lagrangian approach is also explored.

## Lab 03 - Compressive sensing and image denoising

This lab investigates *image reconstruction from incomplete pixel observations*. The reconstruction is posed as a constrained sparsity problem in the two-dimensional Fourier domain, replacing an ideal non-convex sparse formulation with an *l1 convex relaxation*.

The implementation uses *Douglas–Rachford splitting*, alternating complex soft-thresholding with projection onto the observed-pixel consistency constraint. A *greedy Fourier-domain / orthogonal matching pursuit (OMP)* approach serves as a comparison. Experiments and diagnostics include reconstructed images, reconstruction error, convergence behaviour, and the effect of algorithm parameters and sampling ratios.

## More informations on Final oral examination

Topic: Compressive Sensing and Image Denoising (Lab 03).

Presentation date: 16 January 2026. 

Slide: Final oral presentation in PDF. 

The course's final assessment was an oral examination. The instructions called for a 5–10-minute presentation using 3–5 slides, followed by a 5–10-minute discussion with the jury and fellow students. Students were expected to:

1. Reformulate the problem and motivate the choice of an appropriate optimisation method.

2. Explain the method, including parameters, design decisions and implementation choices.

3. Present selected experimental results, prioritising figures and graphs over numerical tables (ideally around three figures), and describe the performance measure and experimental variables.

4. Critically interpret the results and draw a conclusion.

My presentation follows this scientific narrative for Lab 03. It introduces the inverse problem arising from subsampled images, motivates Fourier-domain sparsity and convex relaxation, explains Douglas–Rachford splitting and the greedy baseline, and compares the methods using *normalised mean-square error (NMSE), computation time and visual reconstruction quality*. It also explores sensitivity to the algorithm's free parameters and discusses practical trade-offs.

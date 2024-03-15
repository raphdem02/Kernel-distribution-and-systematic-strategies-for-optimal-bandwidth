# Kernel Distribution and Systematic Strategies for Optimal Bandwidth
by <a href="https://github.com/raphdem02" target="_blank">Raphael Demare</a> and <a href="https://github.com/Thiboss" target="_blank">Thibault Charbonnier</a>.
## Overview
The probability distribution of an asset's returns is crucial in finance for quantifying expected risks and gains. Non-parametric laws, especially kernel laws, are widely used due to their accuracy. These laws require the selection of a free parameter to characterize the density's regularity. Several methods exist for choosing this parameter, such as minimizing the integrated mean square error, using MCMC, maximizing the predictive power through PITs, or maximizing the "complexity" of the estimated density.
The project's goal is to develop a tool for estimating these densities with automatic free parameter selection, applicable to densities in financial contexts, such as forecasting the returns of an option and building a systematic trading strategy. This tool aims to quantify return and risk, thus providing a basis for trading and investment decisions.

## Optimal Bandwidth Selection Method
### Kernel Density Estimation (KDE)

Kernel Density Estimation (KDE) is a non-parametric way to estimate the probability density function of a random variable. The KDE is a fundamental data smoothing problem where inferences about the population are made, based on a finite data sample. Here's a brief definition and the formula used to compute the KDE:

#### Definition
Let
```math
(X_1,...,X_n)
```
be independent data points with Cumulative Distribution Function (C.D.F) (F) and Probability Density Function (P.D.F) (f) with support over the real numbers. The kernel density estimator (KDE) can be defined as:
```math
\hat{f}(x, h) = \frac{1}{nh} \sum_{i=1}^{n} K\left(\frac{x - X_i}{h}\right)
```
where:

- n is the number of data points,
- K is the kernel function, a non-negative function that integrates to one and has mean zero.
- h is the bandwidth or smoothing parameter, a positive parameter that influences the estimator's smoothness.

The choice of the bandwidth h is critical since it controls the trade-off between the bias of the estimator (how close the estimate is to the true density) and its variance (how variable the estimate is across different samples).

#### Various Methods

In the context of Kernel Density Estimation, selecting the appropriate bandwidth is critical for achieving a good balance between bias and variance. We've investigated various methods for this purpose:

- **AMISE (Asymptotic Mean Integrated Squared Error):**
  This method aims to minimize the integrated squared error asymptotically, offering an estimate that reduces the discrepancy between the estimated density and the true underlying density.

- **Silverman's Rule of Thumb:**
  A heuristic based on simplified assumptions about the data distribution, providing a quick, practical initial bandwidth estimate. However, it may not be optimal for all distributions.

- **Leave One Out Cross-Validation (LOOCV):**
  Evaluates different bandwidth choices by omitting one observation at a time, estimating the density with the remaining data, and measuring the error on the omitted observation to strike a balance between bias and variance.

- **MCMC Method (Markov Chain Monte Carlo):**
  Used for simulating distributions that are challenging to compute directly. It can help estimate the probability density and adaptively select the bandwidth.

- **Probability Integral Transform (PIT):**
  Transforms data using their cumulative distribution function, which helps in bandwidth selection by working with data that conforms to a uniform distribution after the transformation.

- **Complexity Method:**
  Based on econophysics, this method maximizes the "complexity" of the estimated density, navigating between overfitting and underfitting to determine the optimal bandwidth.

- **Conditional Version:**
  Adjusts bandwidth selection methods for conditional densities, suitable for estimating densities in scenarios where certain variables are fixed or conditioned by others.

  All this methods were implemented and can be found in the first folder.

## QIS based on optimal bandwidth selection



## Bibliography

- Silverman, B. W. (1986). *Density Estimation for Statistics and Data Analysis*. CRC Press.

- Jones, M. C., Marron, J. S., & Sheather, S. J. (1996). A Brief Survey of Bandwidth Selection for Density Estimation. *Journal of the American Statistical Association*, 91(433), 401-407.

- Tsybakov, A. B. (2003). *Introduction à l'Estimation Non Paramétrique* (Vol. 41). Springer Science & Business Media.

- Zhang, X., Hyndman, R. J., & King, M. L. (2004). Bandwidth Selection for Multivariate Kernel Density Estimation Using MCMC (No. 9/04). Monash University, Department of Econometrics and Business Statistics.

- Harvey, A., & Oryshchenko, V. (2012). Kernel Density Estimation for Time Series Data. *International Journal of Forecasting*, 28(1), 3-14.

- Garcin, M., Klein, J., & Laaribi, S. (2020). Estimation of Time-Varying Kernel Densities and Chronology of the Impact of COVID-19 on Financial Markets. arXiv preprint.

- Garcin, M. (2023). Complexity Measure, Kernel Density Estimation, Bandwidth Selection, and the Efficient Market Hypothesis. arXiv preprint.

- Hyndman, R. J., Bashtannyk, D. M., & Grunwald, G. K. (1996). Estimating and Visualizing Conditional Densities. *Journal of Computational and Graphical Statistics*, 5(4), 315-336.

- Bashtannyk, D. M., & Hyndman, R. J. (2001). Bandwidth Selection for Kernel Conditional Density Estimation. *Computational Statistics & Data Analysis*, 36(3), 279-298.

- Cao, J., Chen, J., Farghadani, S., Hull, J., Poulos, Z., Wang, Z., & Yuan, J. (2023). Gamma and Vega Hedging Using Deep Distributional Reinforcement Learning. *Frontiers in Artificial Intelligence*, 6, 1129370.


  


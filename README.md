# Kernel Distribution and Systematic Strategies for Optimal Bandwidth

## Overview
The probability distribution of an asset's returns is crucial in finance for quantifying expected risks and gains. Non-parametric laws, especially kernel laws, are widely used due to their accuracy. These laws require the selection of a free parameter to characterize the density's regularity. Several methods exist for choosing this parameter, such as minimizing the integrated mean square error, using MCMC, maximizing the predictive power through PITs, or maximizing the "complexity" of the estimated density.
The project's goal is to develop a tool for estimating these densities with automatic free parameter selection, applicable to densities in financial contexts, such as forecasting the returns of an option and building a systematic trading strategy. This tool aims to quantify return and risk, thus providing a basis for trading and investment decisions.

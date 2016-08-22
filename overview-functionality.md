## Overview functionality

There are four main functions in the vpc package:

- `vpc()`: VPC for continuous data
- `vpc_cat()`: VPC for categorical data
- `vpc_cens()`: VPC for censored continuous data (e.g. data < LOQ)
- `vpc_tte()`: VPC for (repeated) time-to-event data

The main arguments to these function are the `sim` and `obs` arguments, which specify a simulation dataset and an observation dataset. All other arguments can be used to customize data parsing and visual appearance of the VPC such as stratification and binning. All four functions will return a ggplot2 object.

## Options

- stratification (single & multiple)
- prediction-correction
- binning methods (K-means clustering, by time, by number of data points, by density, etc).
- automatated number of bins (using Sturges' rule) or manual input of number of bins
- plot without simulated data (`sim=NULL`), or without observed data(`obs=NULL`).
- general-purpose function (`sim_data`) to simulate data from a mixed-effects structural model, a fixed parameter vector and between-subject variability covariance matrix.

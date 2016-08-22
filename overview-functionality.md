## Overview functionality 

Plots:
- VPC for continuous data
- VPC for censored continuous data (e.g. below LOQ)
- VPC for categorical data
- VPC for time-to-event data (single and repeated)
- Kaplan-Meier Mean Covariate plots [KMMC](http://page-meeting.org/pdf_assets/4280-2012-06%20PAGE%20KMMC.pdf)
- *in progress*: npde plots with prediction intervals, see e.g. [here](http://page-meeting.org/pdf_assets/9164-venise12_posternpde.pdf)

Options:
- stratification (single & multiple)
- prediction-correction
- binning methods (K-means clustering, by time, by number of data points, by density, etc).
- automatated number of bins (using Sturges' rule) or manual input of number of bins
- plot without simulated data (`sim=NULL`), or without observed data(`obs=NULL`).
- general-purpose function (`sim_data`) to simulate data from a mixed-effects structural model, a fixed parameter vector and between-subject variability covariance matrix.

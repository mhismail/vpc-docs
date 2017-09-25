# Prediction-correction

An explanation of prediction-correction and why it is (sometimes) necessary is provided in [this article by Bergstrand et al.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3085712). Prediction correction is implemented in this package using the `pred_corr` argument to the `vpc()` function. For example, the following command will perform the prediciton-correction and also plot the observed data:

    vpc (sim = sim, obs = obs, pred_corr = TRUE, show=list(obs_dv = TRUE, obs_ci = TRUE))

_Note: if there is a lower limit to the observations, this needs to be specified too using the `pred_corr_lower_bnd=` argument._

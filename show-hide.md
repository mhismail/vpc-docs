# Showing / hiding elements

Using the `show` argument, you can instruct the `vpc` function what plot elements to show. The defaults are:

    obs_dv = FALSE        # the observed data
    obs_ci = TRUE         # the confidence interval of the observed data
    obs_median = TRUE     # the median of the observed data
    sim_median = FALSE    # the median of the simulated data
    sim_median_ci = TRUE  # the confidence interval around the median of the simulated data
    pi = FALSE            # the prediction interval quantiles
    pi_ci = TRUE          # the confidence interval around the prediction interval quantiles
    pi_as_area = FALSE    # show the PI as area instead of two lines
    bin_sep = TRUE        # show the bin separaters (as geom_rug)

For more information about these elements of the VPC, and e.g. the difference between confidence intervals and prediction intervals, and why it is usually important to show both, please have a look at e.g. [this tutorial about VPCs](http://page-meeting.org/pdf_assets/8694-Karlsson_Holford_VPC_Tutorial_hires.pdf).

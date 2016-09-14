# Appearance

The VPC can be shown in many different ways, which might depend e.g. on the amount of data available, the statistic to evaluate, the message one wants to convey, the target audience, etc. For more information about the elements of the VPC, and e.g. the difference between confidence intervals and prediction intervals, and why it is usually important to show both, please have a look at e.g. [this tutorial about VPCs](http://page-meeting.org/pdf_assets/8694-Karlsson_Holford_VPC_Tutorial_hires.pdf).

Showing and hiding elements, as well as theming of the vpc is explained below.

## Showing / hiding elements

Using the `show` argument, you can instruct the `vpc` function what plot elements to show, e.g.:

    vpc(sim, obs, show = list(obs_dv = TRUE, pi = TRUE))

The arguments specified in the list will overwrite the defaults, which are:

    obs_dv = FALSE        # the observed data
    obs_ci = TRUE         # the confidence interval of the observed data
    obs_median = TRUE     # the median of the observed data
    sim_median = FALSE    # the median of the simulated data
    sim_median_ci = TRUE  # the confidence interval around the median of the simulated data
    pi = FALSE            # the prediction interval quantiles
    pi_ci = TRUE          # the confidence interval around the prediction interval quantiles
    pi_as_area = FALSE    # show the PI as area instead of two lines
    bin_sep = TRUE        # show the bin separaters (as geom_rug)

## Theming

Besides showing / hiding specific elements, colors, fills, transparency (alpha), and linetypes and sizes can be changed easily using the `vpc_theme` argument and function. More general plot theming can be accomplished by supplying a ggplot2 theme to the `ggplot_theme` argument.

    vpc(sim, obs,
        vpc_theme = new_vpc_theme (list(
           sim_pi_fill = "#aa6666", sim_pi_alpha = 0.15,
           sim_median_fill = "#66aa66", sim_median_alpha = 0.3,
           obs_ci_color = "red", obs_ci_linetype = 'solid',
           bin_separators_color = NA))
    )

Any arguments specified to the `vpc_theme` list will overwrite the defaults, which are:

    obs_color = "#000000",
    obs_size = 1,
    obs_median_color = "#000000",
    obs_median_linetype = "solid",
    obs_median_size = 1,
    obs_alpha = .7,
    obs_shape = 1,
    obs_ci_color = "#000000",
    obs_ci_linetype = "dashed",
    obs_ci_size = .5,                       
    sim_pi_fill = "#3388cc",
    sim_pi_alpha = 0.15,  
    sim_pi_color = "#000000",
    sim_pi_linetype = 'dotted',
    sim_pi_size = 1,                     
    sim_median_fill = "#3388cc",
    sim_median_alpha = 0.3,  
    sim_median_color = "#000000",
    sim_median_linetype = "dashed",
    sim_median_size = 1,
    bin_separators_color = "#000000"   

If you'd like to add additional lower-level theming using ggplot-elements, you can just use the standard [theming features](http://docs.ggplot2.org/current/theme.html) available in
ggplot2, e.g.:

    vpc(sim, obs) + theme_bw()

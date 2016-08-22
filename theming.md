# Theming

Additionally, colors, fills, transparency (alpha), and linetypes and sizes can be changed easily using the `vpc_theme` argument and function. More general plot theming can be accomplished by supplying a ggplot2 theme to the `ggplot_theme` argument.

    vpc(sim, obs,
        vpc_theme = new_vpc_theme (list(
           sim_pi_fill = "#aa6666", sim_pi_alpha = 0.15,
           sim_median_fill = "#66aa66", sim_median_alpha = 0.3,
           obs_ci_color = "red", obs_ci_linetype = 'solid',
           bin_separators_color = NA)),
        ggplot_theme = theme_empty
    )

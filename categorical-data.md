# Categorical data

VPCs can also be made for categorical data. These show the probability of observing a specific discrete outcome (or count), and plot this versus the simulated probability, shown as a confidence interval.

    obs_cat <- read_table_nm(file=paste0(system.file(package="vpc"), "/extdata/sdtab45"))
    sim_cat <- read_table_nm(file=paste0(system.file(package="vpc"), "/extdata/simtab45"))
    vpc_cat (sim = sim_cat, obs = obs_cat,
             obs_cols = list(dv = "SMXH"), sim_cols = list(dv = "SMXH"))

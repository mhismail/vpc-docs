# Time-to-event data

Similar to the VPC for continuous data, the VPC for TTE data requires simulated data. In general, there are two distinct approach to simulate survival data:

- *Hazard integration*: Integrate the hazard over time, and at *any possible* observation timepoint randomly draw a binary value based on the probability of observing the event. The disadvantage of this method is that it is slow due to the numerical solving of the ODEs. Also, a dataset with a dense design grid has to be used for simulation, i.e. one that has observation times at every possible timepoint that an event can occur for all individuals.

- *Direct sampling*: Sample event times directly from the distribution used to model the data (e.g. Weibull, exponential, Gompertz). Advantages of this approach is that it is much faster, and it does not require a dense grid. The disadvantage with this approach is however that the hazard is assumed constant over time, so models with time-dependent hazards cannot easily be simulated with this approach. This approach is straightforward in R but cannot easily be implemented in NONMEM. Example will follow soon.

An example for time-to-event data is shown below. The datasets are supplied with the `vpc` library.

    data(rtte_obs_nm)
    data(rtte_sim_nm)

Treat RTTE as TTE, no stratification:

    vpc_tte(sim = rtte_sim_nm,
            obs = rtte_obs_nm,
            rtte = FALSE,
            sim_cols = list(dv = "dv", idv="t"),
            obs_cols = list(idv = "dt"))

Stratified for covariate and study arm, and binned and smooth:

    vpc_tte(sim = rtte_sim_nm,
            obs = rtte_obs_nm,
            stratify = c("sex","drug"),
            rtte = FALSE,
            bins = "kmeans",
            n_bins = 20,
            smooth = TRUE,
            sim_cols = list(dv = "dv", idv="t"),
            obs_cols = list(idv = "dt"))

Stratified for event number (RTTE) and study arm:

    vpc_tte(sim = rtte_sim_nm,
            obs = rtte_obs_nm,
            rtte = TRUE, rtte_calc_diff = TRUE, events = c(1:3),
            stratify=c("drug"),
            bins = "time",
            n_bins = 20,
            smooth = TRUE,
            sim_cols = list(dv = "dv", idv="t"),
            obs_cols = list(idv = "t"), verbose=TRUE)

## Kaplan-Meier Mean Covariate plots (KMMC)

    vpc_tte(sim = rtte_sim_nm,
            obs = rtte_obs_nm,
            rtte = FALSE,
            bins=c(10, 20, 40, 60, 80, 100), # binning is recommended with KMMC
            kmmc = "sex",
            sim_cols = list(dv = "dv", idv="t"),
            obs_cols = list(idv = "dt"))

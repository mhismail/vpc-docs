# Continuous data

Load the library and get the observation data and simulation data.
In the first example, we'll use a dataset that's available in R by default (Theophylline) and generate the simulation dataset in R.

    library(dplyr)

    ## Load the theophylline PK dataset
    obs <- Theoph
    colnames(obs) <- c("id", "wt", "dose", "time", "dv")
    obs <- obs %>%
            group_by(id) %>%
            mutate(sex = round(runif(1))) # randomly assign a "sex" covariate
    sim <- sim_data(obs, # the design of the dataset
                    model = function(x) { # the model
                      pk_oral_1cmt (t = x$time, dose=x$dose * x$wt, ka = x$ka, ke = x$ke, cl = x$cl * x$wt)
                    },
                    error = list(additive = 0.1),
                    theta = c(2.774, 0.0718, .0361),                 # parameter values
                    omega_mat = c(0.08854,                           # specified as lower triangle by default;
                                  0.02421, 0.02241,                  # note: assumed that every theta has iiv, set to 0 if no iiv.
                                  0.008069, 0.008639, 0.02862),
                    par_names = c("ka", "ke", "cl"),                 # link the parameters in the model to the thetas/omegas
                    n = 500)

However, instead we could use observation and simulation data from NONMEM, e.g. (not run):

    message=FALSE, error=FALSE}
    obs <- read_table_nm("sdtab1")   # an output table with at least ID, TIME, DV
    sim <- read_table_nm("simtab1")  # a simulation file with at least ID, TIME, DV

The `read_table_nm()` function (originally written by Benjamin Guiastrennec) comes with the `vpc` library and is a fast way to read in output data created from the $TABLE record in NONMEM, including tables with multiple subproblems.

_Note: If you imported the data from NONMEM, the VPC function will automatically detect column names from NONMEM, such as ID, TIME, DV. If you simulated data in R or got the data from a different software, you will probably have to change the variable names for the dependent and independent variable, and the individual index._

Next, the VPC can simply be created using:

    vpc (sim = sim, obs = obs)


With more explicit use of options, and saving the object:

    vpc(sim = sim,
           obs = obs,                                   # supply simulation and observation dataframes
           obs_cols = list(
             dv = "dv",                               # these column names are the default,
             idv = "time"),                            #   update these if different.
           sim_cols = list(
             dv = "sdv",
             idv = "time"),
           bins = c(0, 2, 4, 6, 8, 10, 16, 25),             # specify bin separators manually
           stratify = c("sex"),                         # multiple stratifications possible, just supply as vector
           pi = c(0.05, 0.95),                          # prediction interval simulated data to show
           ci = c(0.05, 0.95),                          # confidence intervals to show
           pred_corr = FALSE,                           # perform prediction-correction?
           show = list(obs_dv = TRUE),                              # plot observations?
           facet = "rows",                              # wrap stratifications, or as "row" or "column"
           ylab = "Concentration",
            xlab = "Time (hrs)")

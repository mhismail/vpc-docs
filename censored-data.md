# Censored data

The `vpc_cens()` function can be used to create a VPC for the probability of left- or right-censoring such as in the case of data being lower than the lower limit of quantification (<LLOQ) or being above the upper limit of quantification (>ULOQ).

There is no need to add a variable to the dataset to flag the censored cases, the function only requires the `lloq` or `uloq`. Make sure you set the `lloq` or `bloq` cases to any value below or above the limit, respectively.

_Note: do **not** set the values exactly at the limit, since then these values will be assumed to be actually measured at the limit._

The example below artificially induces an LLOQ of 5 for the above model / dataset, and generates a VPC for the probability of left-censoring.

    vpc_cens(sim = simple_data$sim, obs = simple_data$obs, lloq = 30)

The vpc for the uncensored (contionuous) data will show the censoring limit as a horizontal line, and will also visualize the uncensored simulated data below `lloq` or above `uloq`:

    vpc(sim = simple_data$sim, obs = simple_data$obs, lloq = 30)

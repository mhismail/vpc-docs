# Censored data

The `vpc_cens()` function can be used to create a VPC for the probability of left- or right-censoring such as in the case of data <LLOQ or >ULOQ. There is no need to add a variable to the dataset to flag the censored cases, the function only requires the `lloq` or `uloq`. The example below artificially induces an LLOQ of 5 for the above model / dataset, and generates a VPC for the probability of left-censoring.

    vpc_cens(sim, obs, lloq = 5)

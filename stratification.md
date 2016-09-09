# Stratification

Example with stratifcation by covariate `sex`:

    vpc (sim = sim, obs = obs, stratify = c("sex"), facet = "rows")

The `vpc_` functions in this packages allow stratification by 2 variables (horizontal and vertical faceting). If more strata are desired, a new combined variable should be defined that defines the factors.

_Note: The output from the `vpc()` functions are ggplot2-objects, and they can easily be extended and themed using the well-known functions from the ggplot2 package. One cautionary note however is that you should refrain from applying any additional faceting functions after the VPC has been created. In other words, faceting should be done using the `vpc()` functions (`stratify`=... argument). Otherwise you will end up with funky (in the best case) or misleading (in the worst case) plots._

# VPC documentation

The VPC is a widely used diagnostic tool in pharmacometrics (see e.g. [here](http://page-meeting.org/default.asp?abstract=1434)), showing how certain statistics (percentiles) for observed data compare to those same statistics for data simulated from a model. Historically, these plots are most commonly created using [PsN](http://psn.sourceforge.net) and [Xpose](http://xpose.sourceforge.net), using NONMEM as the simulation engine) or with Monolix. The aim of this `vpc` package for R is to provide:

- fully R-based computation of the VPC with plotting handled by `ggplot2`
- package that is more flexible regarding input (use simulated data from R, NONMEM, Monolix, Stan, or any other simulation tool)
- easier to customize, e.g. request any prediction / confidence interval or binning strategy upon plotting.
- easier to extend / theme

The package is available on [CRAN](https://cran.r-project.org/web/packages/vpc/index.html), and is being developed at [GitHub](https://github.com/ronkeizer/vpc). This documentation is still in development, and should be seen as a more convenient overview of core functionality, compared to the more detailed *in-package* help. please let us know if you feel some essential information is missing.

## Quick start

    install.packages("vpc")
    library("vpc")
    vpc(sim = simple_data$sim, obs = simple_data$obs)
    vpc(sim = simple_data$sim, obs = simple_data$obs, lloq = 20)


## License

[MIT license](http://opensource.org/licenses/MIT)

# VPC documentation


The VPC is a widely used diagnostic tool in pharmacometrics (see e.g. [here](http://page-meeting.org/default.asp?abstract=1434)), most commonly created using [PsN](http://psn.sourceforge.net) and [Xpose](http://xpose.sourceforge.net), using NONMEM as the simulation engine. The aim of the current library is to provide an improved tool that is:

- a single-step process for creating a VPC in R (not using Xpose or PsN).
  - e.g. allows changing of vpc parameters such as binning / stratification upon creation of the plot, not in a separate pre-processing step.
  - easier debugging than PsN+Xpose, all data parsing and plotting in one R function
- more flexible regarding input (use simulated data from R, NONMEM, Monolix, Stan, or any other simulation tool)
- easier to customize, e.g. request any prediction / confidence interval or binning strategy upon plotting.
- easier to extend: the output is a ggplot object which can be themed and extended


## Installation

    library("devtools")
    install_github("ronkeizer/vpc")
    library(vpc)
    ?vpc

_NOte: The `data.table` package is installed manually here before the `vpc` package since it often doesn't install automatically. If there are any addtional packages that do not install automatically, use install.package with a proper repository to do so._

## How to use

See [vignette](http://ronkeizer.github.io/vpc/)

## License

[MIT license](http://opensource.org/licenses/MIT)
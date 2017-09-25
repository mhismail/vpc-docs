# Installation

The `vpc` package is on CRAN, so it can conveniently be installed using:

    install.packages("vpc")
    library(vpc)

The development version is available from GitHub. It might have some new features, but might also be less stable, so be careful using that version in a production environment. To be able to install the `vpc` package directly from GitHub you will need to have the `devtools` package installed. On Window, you also need to `Rtools` installed.

    library("devtools")
    install_github("ronkeizer/vpc")
    library(vpc)

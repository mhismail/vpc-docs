# VPC documentation

The VPC is a widely used diagnostic tool in pharmacometrics (see e.g. [here](http://page-meeting.org/default.asp?abstract=1434)), most commonly created using [PsN](http://psn.sourceforge.net) and [Xpose](http://xpose.sourceforge.net) (using NONMEM as the simulation engine) or with Monolix. The aim of the current library is to provide an improved tool that is:

- R-based with plotting handled by `ggplot2`
- more flexible regarding input (use simulated data from R, NONMEM, Monolix, Stan, or any other simulation tool)
- easier to customize, e.g. request any prediction / confidence interval or binning strategy upon plotting.
- easier to extend / theme

## License

[MIT license](http://opensource.org/licenses/MIT)

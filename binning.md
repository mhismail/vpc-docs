# Binning

The vpc functions currently provide three options for binning (`bins=` argument):

- `time`:  Divide bins equally over time (or whatever independent variable is used). Recommended only when there is no observable clustering in the indenpendent variable.
- `data`: Divide bins equally over the amount of data ordered by independent variable. Recommended only when data are for nominal timepoints _and_ all datapoints are available.
- `density`: Divide bins based on data-density, i.e. place the bin-separators at nadirs in the density function. An approximate number of bins can be specified, but it is not certain that the algorithm will strictly use the specified number. More info in `?auto_bin()`.
- `jenks`: Default and recommended method. Jenk's natural breaks optimization, similar to K-means clustering.
- `kmeans`: K-means clustering.
- `pretty`, `quantile`, `hclust`, `sd`, `bclust`, `fisher`. Methods provided by the `classInt` package, see the package help for more information.

Automatic determination of _optimal_ bin number (as described e.g. by Lavielle et al. and Sonehag et al.) will be provided soon.

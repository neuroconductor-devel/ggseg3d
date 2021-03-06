
# ggseg3d <img src='man/figures/logo.png' align="right" height="138.5" />

<!-- badges: start -->

[![Travis build
status](https://travis-ci.com/LCBC-UiO/ggseg3d.svg?branch=master)](https://travis-ci.com/LCBC-UiO/ggseg3d)
[![AppVeyor build
status](https://ci.appveyor.com/api/projects/status/github/LCBC-UiO/ggseg3d?branch=master&svg=true)](https://ci.appveyor.com/project/LCBC-UiO/ggseg3d)
[![Coverage
status](https://codecov.io/gh/LCBC-UiO/ggseg3d/branch/master/graph/badge.svg)](https://codecov.io/gh/LCBC-UiO/ggseg3d)
[![CRAN
status](https://www.r-pkg.org/badges/version/ggseg3d)](https://CRAN.R-project.org/package=ggseg3d)
[![Lifecycle:
maturing](https://img.shields.io/badge/lifecycle-maturing-blue.svg)](https://www.tidyverse.org/lifecycle/#maturing)
[![R build
status](https://github.com/LCBC-UiO/ggseg3d/workflows/R-CMD-check/badge.svg)](https://github.com/LCBC-UiO/ggseg3d/actions)
<!-- badges: end -->

This package mainly contains a plotting function `ggseg3d` and
data.frames of different brain atlases for plotting. Plotting results of
analyses on regions or networks often involves swapping between
statistical tools, like R and Matlab, and software for brain imaging to
correctly visualise analysis results.

This package aims to make it possible to plot results directly through
R.

## Atlases

There are currently four atlases available in the package:

1.  `dk_3d` - Desikan-Killany atlas (aparc).  
2.  `aseg_3d` - Automatic subcortical segmentation.

We are working on creating a detailed description in the wiki on how to
create and contribute atlases to the package. The `ggseg3d` function
already allows you to provide it with a data.frame of a custom atlas if
you have it, but is must correspond to certain specifications to work.

Please see the
[wiki](https://github.com/LCBC-UiO/ggseg/wiki/Creating-and-contributing-atlases)
for information on adding atlases, or inspect the included datasets for
requirements. If anything is unclear in the wiki, give us a shout out in
the issues\!

You may find more atlases in the companion package
[ggsegExtra](https://github.com/LCBC-UiO/ggsegExtra).

## Installation

The package can be installed using {remotes}. The package includes some
large datasets for the brain coordinates. Please be patient during
download and install, it will take some time.

``` r
install.packages("remotes")
remotes::install_github("LCBC-UiO/ggseg3d", build_vignettes = TRUE)
```

The functions are now installed, and you may load them when you want to
use them. All functions are documented in standard R fashion.

## Use

The package also has a vignette, to help you get started using it. You
can access it [here](https://lcbc-uio.github.io/ggseg3d/ggseg3d.html),
or via R:

``` r
library(ggseg3d)
vignette("ggseg3d")
```

``` r
p <- ggseg3d(atlas=dk_3d) %>% 
  remove_axes() %>% 
  pan_camera("right lateral")
```

    #> Warning: `arrange_()` is deprecated as of dplyr 0.7.0.
    #> Please use `arrange()` instead.
    #> See vignette('programming') for more help
    #> This warning is displayed once every 8 hours.
    #> Call `lifecycle::last_warnings()` to see where this warning was generated.

<img src="man/img/README-dk_3d-plot.png" width="700" />

``` r
p <- ggseg3d(atlas=aseg_3d) %>% 
  add_glassbrain() %>% 
  remove_axes() %>% 
  pan_camera("right lateral")
```

<img src="man/img/README-aseg_3d-plot.png" width="700" />

### Report bugs or requests

Don???t hesitate to ask for support using [github
issues](https://github.com/LCBC-UiO/ggseg3d/issues), or requesting new
atlases. While we would love getting help in creating new atlases, you
may also request atlases through the issues, and we will try to get to
it.

# Funding

This tool is partly funded by:

**EU Horizon 2020 Grant:** Healthy minds 0-100 years: Optimising the use
of European brain imaging cohorts (Lifebrain).

**Grant agreement number:** 732592.

**Call:** Societal challenges: Health, demographic change and well-being

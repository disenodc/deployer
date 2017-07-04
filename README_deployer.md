Welcome to the *RECON deployer*!
===============================

The *RECON deployer* can be used to install R packages useful for outbreak
investigation without an internet connection. Follow the instructions below to
use the deployer. **Do not skip steps unless you know what you are doing!**


Thibaut Jombart, 27th June 2017.


### Release notes

This is a beta version of the *RECON deployer*. If you have been given this USB
stick, this means you are officially one of our first testers. Further versions will be made more user-friendly and simpler to use, based on the feedback of this version. To report bugs, suggestions, or ask questions, please post an issue on:

[https://github.com/reconhub/deployer/issues](https://github.com/reconhub/deployer/issues)





<br>

### Installing R 

#### Linux / MacOSX

On linux or MacOSX, it is assumed that a recent installation of R is available
with the toolchain for package development, but installation packages for
RStudio are provided (Debian-based systems only for linux).


#### Windows

Go to the `extra` folder, and install, in this order:

1. Git (`Git-2.13.1-64-bit.exe`)
2. Rtools (`Rtools34.exe`)
3. R (`R-3.4.0-win.exe`)
4. RStudio (`RStudio-1.0.143.exe`)



<br>

### Installing packages using the deployer

To use the *RECON deployer* needs to be activated before installing packages. This is achieved by running the script `activate_deployer`:

```{r eval = FALSE}
source("activate_deployer")
activate_deployer()
```

The function `activate_deployer` requires a path to the *RECON deployer*
folder. By default, it assumes this is the current working directory. The script
will check the content of the deployer, set up a local CRAN repository, and add
a function `install_devel` which can be used to install non-CRAN packages. Note
that in both cases, only the packages which are part of the deployer will be
available. By default, this is a large (~1,000) selection of CRAN packages, plus
all release branches of RECON packages on github.


Once the script has been run, from the same R session, you can install CRAN packages as usual (but without internet), for instance:

```{r eval = FALSE}
install.packages("outbreaks")
```

For non-CRAN packages (i.e. in development, 'devel'), use:
```{r eval = FALSE}
install_devel("earlyR")
```

<br>
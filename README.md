# jampack

R Package containing RNA-seq analysis method suite using the data
by Farris et al, hippocampal subregion-specific mouse transcriptome
data.

## Rmarkdown summary of methods used in Farris et al

An Rmarkdown file was prepared to demonstrate the analysis steps
used for RNA-seq and microarray analysis, and to create the figures
in the manuscript.

[Rmarkdown summary of methods used in Farris et al](https://jmw86069.github.io/jampack/farrisSeq.html)

### Data supporting the manuscript required for Rmarkdown

The raw RNA-seq data supporting the manuscript is required in order
to reproduce the Rmarkdown documentation, and is provided through
an R data package **"farrisdata"** installed via Github using
the **devtools** install function:

>    devtools::install_github("jmw86069/farrisdata")

In addition to installing the "farrisdata" package, install "jampack":

>    devtools::install_github("jmw86069/jampack")

The "jampack" package will install other R package dependencies
and should be sufficient to reproduce the full Rmarkdown HTML output.

Note that "jampack" itself does not require "farrisdata" in order to
avoid having to install a large data package in order to use the RNA-seq
analysis functions. Similarly, the "farrisdata" package does not require
"jampack" since the data itself useful independent of the "jampack" R
packages.

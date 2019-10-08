# jampack

"Jam" suite of data analysis R packages, splicejam sashimi plots,
and supporting methods used in
[Farris et al, 2019. Hippocampal Subregions Express
Distinct Dendritic Transcriptomes that Reveal 
Differences in Mitochondrial Function in CA2](https://www.cell.com/cell-reports/fulltext/S2211-1247(19)31155-6)


### Installation:

>    `devtools::install_github("jmw86069/jampack")`


## Jampack suite of "Jam" R packages <img src="https://raw.githubusercontent.com/jmw86069/splicejam/master/man/figures/splicejam_logo.png" width="133px" height="154px" align="right" style="padding-left:10px;background-color:white;" />

* [splicejam](https://jmw86069.github.io/splicejam/index.html):
Sashimi plots, splicejam R-shiny Sashimi app, various supporting
functions for RNA-seq and gene transcript isoform analysis.
* [jamba](https://jmw86069.github.io/jamba/index.html): ***Jam Ba***se functions
* [jamma](https://jmw86069.github.io/jamma/index.html): ***Jam MA***-plots
* [colorjam](https://jmw86069.github.io/colorjam/index.html): Jam color functions
* [multienrichjam](https://jmw86069.github.io/multienrichjam/index.html): Multi enrichment analysis

Each `"jampack"` R package includes online documentation
linked to its Github page, created by `"pkgdown"`.
Most functions contain examples with online figures
where applicable.

## Methods used in [Farris et al, 2019](https://www.cell.com/cell-reports/fulltext/S2211-1247(19)31155-6)

An Rmarkdown file was prepared to reproduce and demonstrate
the analysis steps used for RNA-seq and microarray analysis,
and which re-creates the figures in the manuscript. This Rmarkdown
file was used to produce an HTML summary:

[HTML summary of methods in Farris et al, 2019](https://jmw86069.github.io/jampack/farrisSeq.html)

### Supporting data for [Farris et al, 2019](https://www.cell.com/cell-reports/fulltext/S2211-1247(19)31155-6)

Additional data required for the Rmarkdown analysis
is provided in an R package ["farrisdata"](https://github.com/jmw86069/farrisdata).
This package can be installed via Github using:

> `devtools::install_github("jmw86069/farrisdata")`

In addition to installing the "farrisdata" package, install "jampack":

> `devtools::install_github("jmw86069/jampack")`

The "jampack" package will install other R package dependencies
and should be sufficient to reproduce the full Rmarkdown HTML output.

Note that "jampack" itself does not require "farrisdata" in order to
avoid having to install a large data package in order to use the RNA-seq
analysis functions. Similarly, the "farrisdata" package does not require
"jampack" since the data itself useful independent of the "jampack" R
packages.

### How to build the HTML report from Rmarkdown

1. Make sure to install "jampack" with all dependencies:

> `devtools::install_github("jmw86069/jampack", dependencies=TRUE);`

2. Download the file ["farrisSeq.Rmd"](https://raw.githubusercontent.com/jmw86069/jampack/master/docs/farrisSeq.Rmd)

* Move this file to a convenient folder.
Cache files and images will be stored in this folder as a result
of the analysis steps.
* Open an R session in the folder where the file was saved,
then run this command in R:

> `rmarkdown::render("farrisSeq.Rmd", "html_document", knit_root_dir=getwd(), output_dir=getwd())`

* Note that when you run `rmarkdown::render()` it will also
populate the active R session with the R objects used,
which can be a convenient way to inspect the data.
* Alternatively, open the `farrisSeq.Rmd` file in Rstudio, and
click `"Knit"` to render the document in HTML. Note that when you
use "Knit" in Rstudio, it does not populate the data into the
active R session by default.

 
## If you encounter problems

1. You may need to install the tool `"pandoc"`, as described
[https://pandoc.org](https://pandoc.org). If you are unable to
install Pandoc, note that Rstudio also installs its own
`"pandoc"`, which can be used outside of Rstudio. To do so,
add the path to the folder containing pandoc to the
environment variable `PATH`.
2. R package dependencies are sometimes difficult to resolve, but
some common errors we observed:

    * Some Bioconductor packages require a higher version of R,
    we have tested and verified versions `R-3.5.*` and `R-3.6.*`.
    * The (amazing) package "ComplexHeatmap" must be version
    `1.99.5` or higher, as of April 2019 required the Github R package;
    as of October 2019 any official Bioconductor release version 2.0.0
    should be sufficient. If you
    see error messages related to ComplexHeatmap, you may try the
    Github development version with
    `devtools::install_github("jokergoo/ComplexHeatmap")`.
    * Other required packages should be installed and imported, but
    in some cases it is helpful to load the package into the user
    environment. For example if a function is not available, loading
    its source package can be a workaround. If you encounter such
    issues, **please** let us know by filing a Github issue. We are
    trying to reduce package dependencies meanwhile.

3. Please file an issue in Github describing the steps you tried, and
the error message you received. It will fill us with happiness to know
that somebody has tried to use the tools, and cares enough to help
us improve.
4. Expert mode: Clone the Github repository, make the fix or update,
then send a pull request to include your updates into the repository.


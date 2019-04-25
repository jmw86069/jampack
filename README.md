# jampack

Suite of RNA-seq analysis R packages, also used
in Farris et al for analysis of hippocampal subregion-specific
mouse transcriptome data.

### Installation:

>    `devtools::install_github("jmw86069/jampack")`


## Required Jam R packages

"jampack" is dependent upon the following Jam R packages, each
of which has its own pkgdown online documentation, with
figures where applicable:

* [**jamba**](https://jmw86069.github.io/jamba/index.html): ***Jam Ba***se functions
* [**jamma**](https://jmw86069.github.io/jamma/index.html): ***Jam MA***-plots
* [**splicejam**](https://jmw86069.github.io/splicejam/index.html):
Functions for RNA-seq and splicing analysis; Sashimi plots; R-shiny Sashimi
app.
* [**colorjam**](https://jmw86069.github.io/colorjam/index.html): Jam color functions


## Methods used in Farris et al

An Rmarkdown file was prepared to reproduce and demonstrate
the analysis steps used for RNA-seq and microarray analysis,
and which create the figures in the manuscript. This Rmarkdown
file was used to produce an HTML summary:

[HTML summary of methods in Farris et al](https://jmw86069.github.io/jampack/farrisSeq.html)

### Farris et al supporting data

Some data is required for the Farris et al Rmarkdown analysis,
which is provided in an R package **"farrisdata"**. It is
installed via Github using **devtools**:

>    `devtools::install_github("jmw86069/farrisdata")`

In addition to installing the "farrisdata" package, install "jampack":

>    `devtools::install_github("jmw86069/jampack")`

The "jampack" package will install other R package dependencies
and should be sufficient to reproduce the full Rmarkdown HTML output.

Note that "jampack" itself does not require "farrisdata" in order to
avoid having to install a large data package in order to use the RNA-seq
analysis functions. Similarly, the "farrisdata" package does not require
"jampack" since the data itself useful independent of the "jampack" R
packages.

### How to build the HTML report from Rmarkdown

1. Make sure to install "jampack" with all dependencies, like this:

> `devtools::install_github("jmw86069/jampack", dependencies=TRUE);`

2. Start with the file "farrisSeq.Rmd" which is provided by the
installed jampack R package. You have a few options:

    * Use R to find the file path, using the command:

    > `system.file("docs", "farrisSeq.Rmd", package="jampack")`

    * Clone the git repository to your local machine. On Linux or Mac,
    open a terminal, run the command
    
    > `git clone https://github.com/jmw86069/jampack.git`
    
    Then navigate to the "jampack/docs" folder.
    
    * **Or** download the `farrisSeq.html` file from Github:
    [farrisSeq.Rmd](https://github.com/jmw86069/jampack/raw/master/docs/farrisSeq.Rmd)

3. Preferably, place the `farrisSeq.html` file into a new, empty folder
on your machine.
4. Navigate to the folder containing the `farrisSeq.Rmd` file.

    * Alternatively, you can navigate your active R session to this
    folder, or if you're really fancy you can point the `rmarkdown::render()`
    command to the full path to the farrisSeq.Rmd file.

5. Open a new R session, preferably with a clean R environment. One way
to confirm opening a clean R environment is to use the command 
`"R --vanilla"`, or to configure Rstudio with the option
unchecked for `"Restore .RData into workplace at startup."`

    > Note: It is best practice not to restore .RData
    to confirm than no previous data will impact new analyses.
    It therefore also promotes reproducible analysis.

6. In your R session run this command:

> `rmarkdown::render("farrisSeq.Rmd", "html_document", knit_root_dir=getwd(), output_dir=getwd())`

* Note the options which help this command behave well:
 
1. "`knit_root_dir=getwd()`" ensures that the new R result files are
created in your current working directory. If you point to the
"`farrisSeq.Rmd`" file in another directory, or use a symbolic
link to the "`farrisSeq.Rmd`" file, this option ensures that the
associated knitr and cache data is created in the current working
directory. Otherwise the default is to create files in the 
same directory that contains the source `.Rmd` file.
2. "`output_dir=getwd()`" ensures that the new HTML report file
is created in the current working directory.
    
#### If you encounter problems rendering "farrisSeq.Rmd"

1. You may need to install "pandoc" to render the HTML page. In principle,
the "rmarkdown" R package should have installed a working version of
pandoc, otherwise install it manually as described at
[https://pandoc.org](https://pandoc.org)
2. R package dependencies are sometimes difficult to resolve, but
some common errors we observed:

    * The package "ComplexHeatmap" must be version `1.99.5` or higher,
    which as of April 2019 required the Github R package. Check the
    version with `packageVersion("ComplexHeatmap")` and if needed,
    install manually `devtools::install_github("jokergoo/ComplexHeatmap")`.
    * Other obscure packages should be installed and imported, but
    in some cases it is helpful to load the package into the user
    environment. For example if a function is not available, loading
    its source package can be a workaround. If you encounter such
    issues, **please** let us know by filing a Github issue. We are
    trying to reduce package dependencies meanwhile.

3. File an issue in Github describing the steps you tried, and
including the error message you received. We will try to respond
and help resolve the issue promptly!


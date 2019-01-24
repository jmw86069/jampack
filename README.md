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

### Rebuilding the Rmarkdown file docs/farrisSeq.Rmd

1. Make sure to install "jampack" with all dependencies, like this:

> devtools::install_github("jmw86069/jampack", dependencies=TRUE);

2. Start with the file "farrisSeq.Rmd" which is provided by the
installed jampack R package. You have a few options:

    * Use R to find the file path, using the command:

    > system.file("docs", "farrisSeq.Rmd", package="jampack")

    * Clone the git repository to your local machine. On Linux or Mac,
    open a terminal, run the command
    
    > git clone https://github.com/jmw86069/jampack.git
    
    Then navigate to the "jampack/docs" folder.
    
    * Download directly from Github:
    [https://github.com/jmw86069/jampack/raw/master/docs/farrisSeq.Rmd](https://github.com/jmw86069/jampack/raw/master/docs/farrisSeq.Rmd)

3. Preferably, place this file into a new, empty, folder on your machine.
4. Navigate to the folder containing the "farrisSeq.Rmd" file

    * Alternatively, you can navigate your active R session to this
    folder, or if you're really fancy you can point the `rmarkdown::render()`
    command to the full path to the farrisSeq.Rmd file.

5. Open a new R session, preferably with a clean R environment. By this I
mean either running "R --vanilla" or configuring Rstudio with options
uncheck for "Restore .RData into workplace at startup."

    * It is best practice not to restore .RData because it prevents
    previous data from impacting new analyses. It therefore also
    promotes reproducible analysis.

6. In your R session run this command to perform necessary analysis steps,
then render the HTML report.

> rmarkdown::render("farrisSeq.Rmd", "html_document", knit_root_dir=getwd(), output_dir=getwd())

* Note the options which help this command behave well:
 
1. "knit_root_dir=getwd()" will ensure that the new R result files are
created in your current working directory. If you point to the
"farrisSeq.Rmd" file in another directory, or created a symbolic
link to the "farrisSeq.Rmd", this option ensures that your new
data is created in your current working directory. Otherwise
by default, new files are created in the directory containing the
actual .Rmd file.
2. "output_dir=getwd()" again this option ensures the new HTML file
is created in your current working directory.
    
#### If you encounter problems rendering "farrisSeq.Rmd"

1. You may need to install "pandoc" to render the HTML page. In principle,
the "rmarkdown" R package should have installed a working version of
pandoc, otherwise install it manually as described at
[https:://pandoc.org](https:://pandoc.org)


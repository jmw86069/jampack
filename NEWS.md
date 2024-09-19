# jampack version 0.0.22.9000

* updated dependencies:

   * splicejam to 0.0.80.900
   * jamba to 0.0.102.900
   * colorjam to 0.0.28.900
   * jamma to 0.0.33.900
   * farrisdata 0.0.10.900 (optional)
   * ComplexHeatmap to 2.15.4 (optional)

* Holding off for now about requiring R-4.0.0, although it might
be necessary in future.
* In future, all Depends may move to Imports, so that packages
will need to be loaded properly rather than being loaded via
jampack itself. Unclear.

# jampack version 0.0.21.9000

## updated dependencies on splicejam to 0.0.75.900

## changes

* Edits to README.md and farrisSeq.Rmd to include link to the
paper in Cell Reports.

# jampack version 0.0.20.9000

## changes

* `farrisSeq.Rmd` was updated to include links to GEO, and to
re-word several paragraphs to match updated figure numbering.

# jampack version 0.0.19.9000

## changes

* `farrisSeq.Rmd` was updated to include Sashimi plots via
the `"splicejam"` package. Also, description of MultiEnrichMap
methods were included, referencing the `"multienrichjam"` R
package.

# jampack version 0.0.18.9000

## changes

* Updated DESCRIPTION with higher required package version
numbers for jamba, splicejam, jamma, colorjam, to force
updates for those packages as needed.

# jampack version 0.0.17.9000

## changes

* `farrisSeq.Rmd` was updated to include prefixes for
tidyselect functions, including `tidyselect::ends_with()`,
`tidyselect::contains()`, and `tidyselect::matches()`.
Also added tidyselect to packages loaded at the start of
the Rmd.
* Added `dplyr` and `tidyselect` to `"Suggests:" in the
DESCRIPTION file, as they are required by `farrisSeq.Rmd`
but not required otherwise.

# jampack version 0.0.16.9000

## changes

* `splicejam::defineDetectedTx()` was updated to allow conversion
of zero expression values to `NA`, slightly improving the accuracy
of transcript group mean expression values, which is the new default.
For consistency, `zeroAsNA=FALSE` was added to farrisSeq.html to ensure
consistency with previous calculations.
* Updated the README.md page to include direct links to
the online documentation for each Jam R package.
* Reduced the number of files included in the R package build.

# jampack version 0.0.15.9000

## changes

* Updated farrisSeq.Rmd to use prefixed `ComplexHeatmap::draw()`
instead of `draw()` because of R method dispatch errors when
another package is loaded that defines a generic `draw()` function.
* Also confirmed that ComplexHeatmap requires the Github version,
which provides `Heatmap()` arguments such as `left_annotation`. It
should be available on Bioconductor after the next Bioconductor release
(as of April 21, 2019.)

# jampack version 0.0.14.9000

* Export per-gene isoform summary statistics to Excel xlsx files,
with each contrast in its own worksheet. Requires jamba (>= 0.0.29.900).
* Fixed issue where numTx was not reported from runDiffSplice(), resolved
in splicejam (>= 0.0.14.900). Updated DESCRIPTION to add this version
requirement.

# jampack version 0.0.13.9000

* Differential isoform analysis, experiment design and contrast definitions
added to Rmarkdown.

# jampack version 0.0.12.9000

* ALE violin plot implemented, requires splicejam v0.0.11.900 or higher.

# jampack version 0.0.11.9000

* Further ALE analysis steps.

# jampack version 0.0.10.9000

* Added section for ALE processing, and comparison of
proximal to distal ALE regions.

# jampack version 0.0.9.9000

* Requires splicejam 0.0.26.900 for several new functions.
* Added methods for ALE for proximal-distal ALE analysis.

# jampack version 0.0.8.9000

* Moved "library()" calls to the Rmarkdown body, they
should be displayed in the HTML output so others can copy-paste
them to test the R code.

# jampack version 0.0.7.9000

* Added stacked bar chart for transcript types by Neuronal
Transcript List.
* Created "detected" Neuronal Transcript Lists, which is used
to describe the transcript types.
* Modified detectedTxTPManyL to use CB and DE samples, as was
done originally and in the manuscript.
* Enhanced the heatmap of Neuronal Transcripts, using newer
options in ComplexHeatmap on Github which are not yet on Bioconductor.
Depends was updated to point to Github, will be changed to
Bioconductor once it is released there.
* Added rmarkdown to Suggested packages, since it is required
to render the farrisSeq.Rmd file.
* Added instructions for building the farrisSeq.Rmd HTML report.
* Removed liao_style.css which was mostly useful for customized
table rendering, and is not necessary for this Rmarkdown file.
* Incremented some required version numbers for other Jam packages.

# jampack version 0.0.6.9000

* Added Rmarkdown cache.extra to the "docs/farrisSeq.Rmd" file,
dependent upon package versions of  "farrisdata" (in the event the
source data changes), and "splicejam", "jamba" (packages which
provide some key data manipulation functions.)
* Added transcript type definitions per transcript list.
* Added Suggests for "png" and "Cairo" packages, which should help
with ComplexHeatmap.
* Added `colorSub` section to the visible Rmarkdown body, previously
it was in the header but was not visible, therefore making it difficult
to reproduce the workflow by copy-pasting from the rendered HTML
code blocks.
* Added specific R package versions to the DESCRIPTION, to ensure
jampack will require important versioned changes in Jam packages
as needed.

# jampack version 0.0.5.9000

* Added specific sections for supplemental figure 7, for
each panel.
* Added heatmap of expression data using ComplexHeatmap
instead of heatmap.3(). Will assess adding text labels
onto the color bars beside and at the top of the plot.

# jampack version 0.0.4.9000

* Updated README.md with more specific instructions on installing
jampack and farrisdata, in order to reproduce the Rmarkdown HTML
output.
* Fixed typo in the description of Gene data matrix, which represents
Salmon pseudocounts and not TPM values.

# jampack version 0.0.3.9000

## changes to package dependencies

* `farrisdata` and `seqinr` were added to Suggests,
since they are required for building the `docs/farrisSeq.Rmd`
but are otherwise not required for the package.
* Added 3 prime UTR length and CAI analysis sections, along with
support functions updated in splicejam.


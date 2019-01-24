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


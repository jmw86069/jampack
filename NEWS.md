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


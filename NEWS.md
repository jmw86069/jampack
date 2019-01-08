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


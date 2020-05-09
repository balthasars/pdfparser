
# pdfparser

<!-- badges: start -->
<!-- badges: end -->

{pdfparser} provides tools for dealing with text extraction from PDFs.

It comes in handy when you do not only want to read in the text, for which I recommendbut also want
to deal with PDF coordinates of the words, lines and blocks.

Right now its only function is `read_bbox_layout_xhtml()` which parses XHTML files
from `pdftotext`, part of `poppler-utils` (manual can be found [here](https://www.mankier.com/1/pdftotext)).

## Installation

You can install {pdfparser} using:

``` r
devtools::devtools::install_github("balthasars/pdfparser")
```

It is not on CRAN yet.

## Example


``` r
library(pdfparser)
doc <- system.file("extdata", "edi_2009_frcho43c6mmlx5lyohqy_doc#immrrkosg.html", package = "pdfparser")
read_pdf_layout(doc)
```

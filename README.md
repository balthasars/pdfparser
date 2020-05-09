
<!-- README.md is generated from README.Rmd. Please edit that file -->

# `{pdfparser}`

<!-- badges: start -->

<!-- badges: end -->

{pdfparser} provides tools for dealing with text extraction from PDFs.

It comes in handy when you do not only want to read in the text, for
which I recommendbut also want to deal with PDF coordinates of the
words, lines and blocks.

Right now its only function is `read_bbox_layout_xhtml()` which parses
XHTML files from `pdftotext`, part of `poppler-utils` (manual can be
found [here](https://www.mankier.com/1/pdftotext)).

## Installation

You can install the development version from
[GitHub](https://github.com/balthasars/pdfparser) with:

``` r
# install.packages("devtools")
devtools::install_github("balthasars/pdfparser")
```

## Example

This is a basic example which shows you how to solve a common problem:

``` r
library(pdfparser)
doc <- system.file("extdata", "edi_2009_frcho43c6mmlx5lyohqy_doc#immrrkosg.html", package = "pdfparser")
read_bbox_layout_xhtml(doc)
#> # A tibble: 455 x 17
#>    block_attr_xmin block_attr_ymin block_attr_xmax block_attr_ymax
#>    <chr>           <chr>           <chr>           <chr>          
#>  1 167.400000      35.480000       457.740540      70.611000      
#>  2 167.400000      35.480000       457.740540      70.611000      
#>  3 167.400000      35.480000       457.740540      70.611000      
#>  4 167.400000      35.480000       457.740540      70.611000      
#>  5 167.400000      35.480000       457.740540      70.611000      
#>  6 167.400000      35.480000       457.740540      70.611000      
#>  7 167.400000      35.480000       457.740540      70.611000      
#>  8 167.400000      35.480000       457.740540      70.611000      
#>  9 167.400000      35.480000       457.740540      70.611000      
#> 10 167.400000      88.880000       221.400000      96.888000      
#> # … with 445 more rows, and 13 more variables: line_attr_xmin <chr>,
#> #   line_attr_ymin <chr>, line_attr_xmax <chr>, line_attr_ymax <chr>,
#> #   word_attr_xmin <chr>, word_attr_ymin <chr>, word_attr_xmax <chr>,
#> #   word_attr_ymax <chr>, word_value <chr>, page_attr_width <chr>,
#> #   page_attr_height <chr>, doc_name <chr>, page_nr <int>
```

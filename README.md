
<!-- README.md is generated from README.Rmd. Please edit that file -->
huxtable is a package for creating HTML and LaTeX tables. It provides similar functionality to xtable, with a simple interface. Here's a quick example:

``` r
library(huxtable)

ht <- huxtable(a = 1:5, b = letters[1:5])
align(ht)[,2] <- 'right'
bgcolor(ht) <- 'yellow'
border_bottom(ht) <- c(1, 0, 0, 0, 1)
to_html(ht)
to_latex(ht)
```

Or the same thing with a more dplyr-ish syntax:

``` r
library(huxtable)

ht <- huxtable(a = 1:5, b = letters[1:5]) %>% 
      set_align(1:5, 2, 'right') %>% 
      set_bgcolor(1:5, 1:2, 'yellow') %>% 
      set_border_bottom(1:5, 1:2, c(1, 0, 0, 0, 1))

to_html(ht)
to_latex(ht)
```

To see more details, look at [testing-doc.html](testing-doc.html).

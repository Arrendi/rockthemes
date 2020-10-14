rockthemes
================

# <img src="man/figures/logo.png" width="160px" align="right" />

<!-- badges: start -->

[![Build
Status](https://travis-ci.com/johnmackintosh/rockthemes.svg?branch=main)](https://travis-ci.com/johnmackintosh/rockthemes)
<!-- badges: end -->

## What?

This is a collection of colour palettes based on classic rock album
covers.

Although ‘rock’ may be a stretch in some cases, the albums were chosen
for their appealing covers

## Why?

Because [this repo of Metallica inspired
palettes](https://github.com/johnmackintosh/metallicaRt) has been
received quite well on various social media platforms

## Credit

[Thanks to Ryo for the tvthemes
package](https://github.com/Ryo-N7/tvthemes) which helped me get this
off the ground quickly

## Installation

This will probably not go to CRAN, so please install using the remotes
package.

``` r
#library(remotes)
#remotes::install_github("johnmackintosh/rockthemes")
library(rockthemes)
#> Warning: replacing previous import 'vctrs::data_frame' by 'tibble::data_frame'
#> when loading 'dplyr'
library(ggplot2)
library(dplyr)
#> 
#> Attaching package: 'dplyr'
#> The following objects are masked from 'package:stats':
#> 
#>     filter, lag
#> The following objects are masked from 'package:base':
#> 
#>     intersect, setdiff, setequal, union
library(scales)
library(gapminder)
```

## Short Palettes

Only 4 colours, but very nice

``` r
rock_palette("californication")
```

![](man/figures/README-unnamed-chunk-2-1.png)<!-- -->

``` r
rock_palette("coltrane")
```

![](man/figures/README-unnamed-chunk-3-1.png)<!-- -->

``` r
rock_palette("electric")
```

![](man/figures/README-unnamed-chunk-4-1.png)<!-- -->

``` r
rock_palette("faithnomore")
```

![](man/figures/README-unnamed-chunk-5-1.png)<!-- -->

``` r
rock_palette("gogo")
```

![](man/figures/README-unnamed-chunk-6-1.png)<!-- -->

``` r
rock_palette("gunsnroses")
```

![](man/figures/README-unnamed-chunk-7-1.png)<!-- -->

``` r
rock_palette("harvey")
```

![](man/figures/README-unnamed-chunk-8-1.png)<!-- -->

``` r
rock_palette("heap")
```

![](man/figures/README-unnamed-chunk-9-1.png)<!-- -->

``` r
rock_palette("husker")
```

![](man/figures/README-unnamed-chunk-10-1.png)<!-- -->

``` r
rock_palette("janelle")
```

![](man/figures/README-unnamed-chunk-11-1.png)<!-- -->

``` r
rock_palette("maiden")
```

![](man/figures/README-unnamed-chunk-12-1.png)<!-- -->

``` r
rock_palette("metallica")
```

![](man/figures/README-unnamed-chunk-13-1.png)<!-- -->

``` r
rock_palette("miles")
```

![](man/figures/README-unnamed-chunk-14-1.png)<!-- -->

``` r
rock_palette("muse")
```

![](man/figures/README-unnamed-chunk-15-1.png)<!-- -->

``` r
rock_palette("nevermind")
```

![](man/figures/README-unnamed-chunk-16-1.png)<!-- -->

``` r
rock_palette("oasis")
```

![](man/figures/README-unnamed-chunk-17-1.png)<!-- -->

``` r
rock_palette("swift")
```

![](man/figures/README-unnamed-chunk-18-1.png)<!-- -->

``` r
rock_palette("tencc")
```

![](man/figures/README-unnamed-chunk-19-1.png)<!-- -->

## 10 colour palettes for ggplot2 use

``` r
show_col(californication_pal()(10))
```

![](man/figures/README-unnamed-chunk-20-1.png)<!-- -->

``` r
show_col(coltrane_pal()(10))
```

![](man/figures/README-unnamed-chunk-21-1.png)<!-- -->

``` r
show_col(electric_pal()(10))
```

![](man/figures/README-unnamed-chunk-22-1.png)<!-- -->

``` r
show_col(gogo_pal()(10))
```

![](man/figures/README-unnamed-chunk-23-1.png)<!-- -->

``` r
show_col(gunsnroses_pal()(10))
```

![](man/figures/README-unnamed-chunk-24-1.png)<!-- -->

``` r
show_col(harvey_pal()(10))
```

![](man/figures/README-unnamed-chunk-25-1.png)<!-- -->

``` r
show_col(heap_pal()(10))
```

![](man/figures/README-unnamed-chunk-26-1.png)<!-- -->

``` r
show_col(husker_pal()(10))
```

![](man/figures/README-unnamed-chunk-27-1.png)<!-- -->

``` r
show_col(janelle_pal()(10))
```

![](man/figures/README-unnamed-chunk-28-1.png)<!-- -->

``` r
show_col(maiden_pal()(10))
```

![](man/figures/README-unnamed-chunk-29-1.png)<!-- -->

``` r
show_col(metallica_pal()(10))
```

![](man/figures/README-unnamed-chunk-30-1.png)<!-- -->

``` r
show_col(miles_pal()(10))
```

![](man/figures/README-unnamed-chunk-31-1.png)<!-- -->

``` r
show_col(muse_pal()(10))
```

![](man/figures/README-unnamed-chunk-32-1.png)<!-- -->

``` r
show_col(nevermind_pal()(10))
```

![](man/figures/README-unnamed-chunk-33-1.png)<!-- -->

``` r
show_col(oasis_pal()(10))
```

![](man/figures/README-unnamed-chunk-34-1.png)<!-- -->

``` r
show_col(real_thing_pal()(10))
```

![](man/figures/README-unnamed-chunk-35-1.png)<!-- -->

``` r
show_col(taylor_pal()(10))
```

![](man/figures/README-unnamed-chunk-36-1.png)<!-- -->

``` r
show_col(tencc_pal()(10))
```

![](man/figures/README-unnamed-chunk-37-1.png)<!-- -->

``` r
data <- gapminder::gapminder %>% 
    filter(country %in% c("France", "Germany", "Ireland", "Italy", "Japan")) %>% 
    mutate(year = as.Date(paste(year, "-01-01", sep = "", format = '%Y-%b-%d')))

ggplot(data = data, aes(x = year, y = gdpPercap, fill = country)) +
    geom_area(alpha = 0.8) +
    scale_x_date(breaks = data$year, date_labels = "%Y") +
    scale_y_continuous(expand = c(0, 0), labels = scales::dollar) +
    scale_fill_taylor()
```

![](man/figures/README-unnamed-chunk-38-1.png)<!-- -->

``` r
    
ggplot(data = data, aes(x = year, y = gdpPercap, fill = country)) +
    geom_area(alpha = 0.8) +
    scale_x_date(breaks = data$year, date_labels = "%Y") +
    scale_y_continuous(expand = c(0, 0), labels = scales::dollar) +
    scale_fill_tencc()
```

![](man/figures/README-unnamed-chunk-38-2.png)<!-- -->

``` r
    
    ggplot(data = data, aes(x = year, y = gdpPercap, fill = country)) +
    geom_area(alpha = 0.8) +
    scale_x_date(breaks = data$year, date_labels = "%Y") +
    scale_y_continuous(expand = c(0, 0), labels = scales::dollar) +
    scale_fill_husker()
```

![](man/figures/README-unnamed-chunk-38-3.png)<!-- -->

``` r
    
    
    ggplot(data = data, aes(x = year, y = gdpPercap, fill = country)) +
    geom_area(alpha = 0.8) +
    scale_x_date(breaks = data$year, date_labels = "%Y") +
    scale_y_continuous(expand = c(0, 0), labels = scales::dollar) +
    scale_fill_janelle()
```

![](man/figures/README-unnamed-chunk-38-4.png)<!-- -->

``` r
    
    
    ggplot(data = data, aes(x = year, y = gdpPercap, fill = country)) +
    geom_area(alpha = 0.8) +
    scale_x_date(breaks = data$year, date_labels = "%Y") +
    scale_y_continuous(expand = c(0, 0), labels = scales::dollar) +
    scale_fill_californication()
```

![](man/figures/README-unnamed-chunk-38-5.png)<!-- -->

``` r
    
    ggplot(data = data, aes(x = year, y = gdpPercap, fill = country)) +
    geom_area(alpha = 0.8) +
    scale_x_date(breaks = data$year, date_labels = "%Y") +
    scale_y_continuous(expand = c(0, 0), labels = scales::dollar) +
    scale_fill_miles()
```

![](man/figures/README-unnamed-chunk-38-6.png)<!-- -->

``` r
    
    
    ggplot(data = data, aes(x = year, y = gdpPercap, fill = country)) +
    geom_area(alpha = 0.8) +
    scale_x_date(breaks = data$year, date_labels = "%Y") +
    scale_y_continuous(expand = c(0, 0), labels = scales::dollar) +
    scale_fill_muse()
```

![](man/figures/README-unnamed-chunk-38-7.png)<!-- -->


# Strength tests

``` r
library(ggplot2)

dat <- read.csv("data/strength.csv")

dat$rep <- substring(dat$sample, 2, 2)
dat$sample <- substring(dat$sample, 1, 1)
dat$reliability <- "Reliable"
dat$reliability[dat$height < 1] <- "Unreliable"

ggplot(dat, aes(x=sample, y=strength_psi, fill=reliability)) +
  geom_boxplot() +
  scale_y_log10()
```

![](README_files/figure-gfm/unnamed-chunk-1-1.png)<!-- -->

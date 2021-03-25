# `renv`/`targets` dependency discovery issue


## Background

`renv::dependencies()` is not detecting packages specified in `targets::tar_option_set(packages = ...)`, and `renv::hydrate()` is not detecting and installing them. 

This repo uses `renv` and the minimal example in the [targets book](https://books.ropensci.org/targets/walkthrough.html#about-this-minimal-example).

The lockfile `renv.lock` was generated by running `renv::hydrate()` followed by `renv::snapshot()`.

## To reproduce:

1. Clone repo
2. Open `renv-target-issue.Rproj`
2. Run `renv::restore()`
3. Run `targets::tar_make()`

```r
# sessionInfo()
R version 4.0.3 (2020-10-10)
Platform: x86_64-apple-darwin17.0 (64-bit)
Running under: macOS Catalina 10.15.7

Matrix products: default
BLAS:   /System/Library/Frameworks/Accelerate.framework/Versions/A/Frameworks/vecLib.framework/Versions/A/libBLAS.dylib
LAPACK: /Library/Frameworks/R.framework/Versions/4.0/Resources/lib/libRlapack.dylib

locale:
[1] en_US.UTF-8/en_US.UTF-8/en_US.UTF-8/C/en_US.UTF-8/en_US.UTF-8

attached base packages:
[1] stats     graphics  grDevices datasets  utils     methods   base     

loaded via a namespace (and not attached):
 [1] igraph_1.2.6      rstudioapi_0.13   magrittr_2.0.1    tidyselect_1.1.0  R6_2.5.0          rlang_0.4.10     
 [7] fansi_0.4.2       tools_4.0.3       targets_0.2.0     data.table_1.14.1 utf8_1.2.1        cli_2.3.1        
[13] withr_2.4.1       ellipsis_0.3.1    assertthat_0.2.1  digest_0.6.27     tibble_3.1.0      lifecycle_1.0.0  
[19] crayon_1.4.1      processx_3.4.5    purrr_0.3.4       callr_3.5.1       vctrs_0.3.6       ps_1.6.0         
[25] codetools_0.2-18  glue_1.4.2        compiler_4.0.3    pillar_1.5.1      renv_0.13.0       pkgconfig_2.0.3  
```
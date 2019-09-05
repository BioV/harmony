# Harmony <img src="man/figures/logo.png" align="right" alt="" width="120" />

Harmony is a general-purpose R package with an efficient algorithm for integrating multiple data sets. It is especially useful for large datasets such as single-cell RNA-seq.

Harmony is:

- **Fast:** Analyze thousands of cells on your laptop.
- **Sensitive:** Different cell types may be present or absent in each batch.
- **Accurate:** Integrate cells from multiple donors, tissues – even different technologies.

Below, we show how Harmony aligns single-cell RNA-seq data sets from three
different donors. After alignment, it is easier to identify similar cell types
across the donors.

<p align="center">
<img src="https://i.imgur.com/g76m6Mx.gif" style="max-width:40%;">
</p>

Harmony can also be used for batch correction and meta analysis of cells from
different donors, donors, and technologies.

If you use Harmony for published work, please cite the original manuscript.

<div class="well">
<p><b>Fast, sensitive, and accurate integration of single cell data with Harmony</b></p>
<p>Ilya Korsunsky, Jean Fan, Kamil Slowikowski, Fan Zhang, Kevin Wei, Yuriy
Baglaenko, Michael Brenner, Po-Ru Loh, Soumya Raychaudhuri</p>
<p><i>bioRxiv</i> 2019. <a href="https://doi.org/10.1101/461954">doi.org/10.1101/461954</a></p>
</div>

We will share the code needed to reproduce results from the manuscript at
<https://github.com/immunogenomics/harmony2019>. 

# Installation

The easiest way to get Harmony is to install it from Github:

```r
# install.packages("devtools")
devtools::install_github("immunogenomics/harmony")
```

Harmony has been tested on R versions >= 3.4 on Linux, OS X, and Windows.

# Usage

Run the `HarmonyMatrix()` function on your PCs from principal component analysis:

```r
library(harmony)

harmonized_pcs <- HarmonyMatrix(
  data_mat  = pcs,       # Matrix with coordinates for each cell (row) along many PCs (columns)
  meta_data = meta_data, # Dataframe with information for each cell (row)
  vars_use  = "dataset", # Column in meta_data that defines dataset for each cell
  do_pca    = FALSE      # Since we are providing PCs, do not run PCA
)
```

# Documentation

Check out the [Harmony website][website] for more information.

[website]: https://slowkow.github.io/harmony

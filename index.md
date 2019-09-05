# Harmony <img src="man/figures/logo.png" align="right" alt="" width="150" />

Harmony is a general-purpose R package with an efficient algorithm for
integrating multiple data sets. It is especially useful for large single-cell
datasets such as single-cell RNA-seq.

Harmony is:

- **Fast:** Analyze thousands of cells on your laptop.
- **Sensitive:** Different cell types may be present or absent in each batch.
- **Accurate:** Integrate cells from multiple donors, tissues -- even different
  technologies.

<div class="container-fluid"></div>

<div class="card-deck">
  <div class="card">
    <img class="card-img-top" src="articles/main.jpg" alt="Steps in the Harmony algorithm">
    <div class="card-body">
      <h5 class="card-title">Getting started</h5>
      <p class="card-text">See how to use Harmony with your data and integrate
      it into your analysis pipeline.</p>
      <p><a href="articles/quickstart.html" class="card-link">Read →</a></p>
    </div>
  </div>
  <div class="card">
    <img class="card-img-top" src="articles/advanced.png" alt="Cells colored by dataset and cell type">
    <div class="card-body">
      <h5 class="card-title">Advanced tutorial</h5>
      <p class="card-text">Find out more about the internal data structures and algorithm details in this tutorial.</p>
      <p><a href="advanced.html" class="card-link">Read →</a></p>
    </div>
  </div>
  <div class="card">
    <img class="card-img-top" src="https://i.imgur.com/eAPbMJN.gif" alt="Animation of harmony" style="max-height:200px">
    <div class="card-body">
      <h5 class="card-title">Animation</h5>
      <p class="card-text">Visualize how Harmony aligns single-cell RNA-seq datasets from three different donors.</p>
      <p><a href="https://slowkow.com/notes/harmony-animation" class="card-link">Read →</a></p>
    </div>
  </div>
</div>

# Installation

The easiest way to get Harmony is to install it from Github:

```r
# install.packages("devtools")
devtools::install_github("immunogenomics/harmony")
```

Harmony has been tested on R versions >= 3.4 on Linux, macOS, and Windows.

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

# Citation

If you use Harmony for published work, please cite our manuscript:

<div class="border border-secondary rounded p-3 m-3">
<p><b>Fast, sensitive, and accurate integration of single cell data with Harmony</b></p>
<p>Ilya Korsunsky, Jean Fan, Kamil Slowikowski, Fan Zhang, Kevin Wei, Yuriy
Baglaenko, Michael Brenner, Po-Ru Loh, Soumya Raychaudhuri</p>
<p class="mb-0"><i>bioRxiv</i> 2019. <a href="https://doi.org/10.1101/461954">doi.org/10.1101/461954</a></p>
</div>

We will share the code needed to reproduce results from the manuscript at
<https://github.com/immunogenomics/harmony2019>. 



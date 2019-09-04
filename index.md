# Harmony <img src="man/figures/logo.png" align="right" alt="" width="150" />

Harmony is a general-purpose R package with an efficient algorithm for
integrating multiple data sets. It is especially useful for large single-cell
datasets such as single-cell RNA-seq.

Harmony is:

- **Fast:** Analyze thousands of cells on your laptop.
- **Sensitive:** Different cell types may be present or absent in each batch.
- **Accurate:** Integrate cells from multiple donors, tissues, and even totally
  different technologies.

<div class="container-fluid"></div>

<div class="row">

  <div class="col-xs-4">
    <div class="thumbnail">
      <img src="articles/main.jpg" alt="Steps in the Harmony algorithm"">
      <div class="caption">
        <h3>Getting started</h3>
				<p>See how to use Harmony with any data, or integrate it with your Seurat pipeline.</p>
        <p><a href="articles/quickstart.html" class="btn btn-primary" role="button">Learn more</a></p>
      </div>
    </div>
  </div>

  <div class="col-xs-4">
    <div class="thumbnail">
      <img src="articles/advanced.png" alt="Cells colored by dataset or cell type">
      <div class="caption">
        <h3>Detailed tutorial</h3>
				<p>Read about the internal data structures and algorithm details.</p>
        <p><a href="advanced.html" class="btn btn-primary" role="button">Learn more</a></p>
      </div>
    </div>
  </div>

  <div class="col-xs-4">
    <div class="thumbnail">
      <img src="https://i.imgur.com/eAPbMJN.gif" alt="Animation of harmony">
      <div class="caption">
        <h3>Harmony in motion</h3>
				<p>Animation helps to visualize how Harmony aligns three single-cell
				RNA-seq data sets from different donors.</p>
        <p><a href="#" class="btn btn-primary" role="button">Learn more</a></p>
      </div>
    </div>
  </div>

</div>

If you use Harmony for published work, please cite our manuscript:

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


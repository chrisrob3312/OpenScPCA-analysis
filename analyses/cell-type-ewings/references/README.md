# Reference files

This directory contains reference files used for cell typing Ewing sarcoma samples from SCPCP000015.

## Tumor marker genes

`tumor-marker-genes.tsv` contains a list of marker genes used to identify tumor cells in previously published studies.
Currently, this list only contains genes that should mark all tumor cells and we are not yet considering subsets of tumor cells.

The marker gene list was created using gene lists from two publications:

1. Visser, Bleijs, _et al._ (2023) https://doi.org/10.1158/2767-9764.CRC-23-0027 - Marker genes were obtained from the list in [Supplemental Methods under `Cell annotation using external data`](https://aacr.silverchair-cdn.com/aacr/content_public/journal/cancerrescommun/3/10/10.1158_2767-9764.crc-23-0027/1/crc-23-0027-s01.pdf).

2. Goodspeed _et al._ (2024) https://doi.org/10.1101/2024.01.18.576251 - Marker genes were determined to be those that were unique to Ewing sarcoma cells in Figure 1C and 1F.
Only genes that were consistently expressed across Ewing sarcoma tumor cells with little expression in non-malignant cell types were chosen as marker genes.

## All marker genes

`all-marker-genes.tsv` contains a list of marker genes used to identify tumor cells and normal cells.
This currently contains all genes in `tumor-marker-genes.tsv` and genes used to identify normal cells in [Visser, Beligs, _et al._ (2023)](https://doi.org/10.1158/2767-9764.CRC-23-0027) as indicated in the supplemental methods.

## Panglao marker genes

`PanglaoDB_markers_2020-03-27.tsv` is the full set of marker genes exported from [PanglaoDB](https://panglaodb.se), versioned at the given date

## CellAssign References

The `cellassign_refs` folder contains any binary matrices that are used as references when running `CellAssign`.

Both of these files were created in `01-marker-gene-classification-cellassign.Rmd`:

1. `tumor-marker-cellassign.tsv`: This file contains a binary matrix with all genes in `tumor-marker-genes.tsv`.
2. `filtered-tumor-marker-cellassign.tsv`: This file contains a binary matrix with only the genes that have mean gene expression > 1 in SCPCS000490.
3. `visser-all-marker-cellassign.tsv`: This file contains a binary matrix with all marker genes in `tumor-marker-genes.tsv` and all markers for normal cells identified in the Supplemental methods of [Visser et al.,](https://doi.org/10.1158/2767-9764.CRC-23-0027).
4. `panglao-endo-fibro-cellassign.tsv`: This file contains a binary matrix with all marker genes for endothelial cells and fibroblasts from `PanglaoDB_markers_2020-03-27.tsv` and all tumor markes from `tumor-marker-genes.tsv`.

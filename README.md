Markdown
A multi-scale ecological approach to assessing antimicrobial resistance across freshwater systems

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.21476186.svg)](https://doi.org/10.5281/zenodo.21476186)

This repository houses the reproducible analytical pipeline and spatial modeling architectures evaluating landscape, climatic, and local drivers of antimicrobial resistance (AMR) in freshwater systems across Vancouver Island, B.C.

Repository Directory & Structure

Master Scripts

AMR_rf_models_GIT.Rmd: The master, fully annotated R Markdown code execution file running stability-based Random Forest feature selection, spatial regression-kriging, and spatial Leave-One-Out Cross-Validation (LOOCV).
AMR_rf_models_GIT.html: The compiled/knitted HTML document. Open this file to immediately view all statistical summaries, model performance metrics, and spatial diagnostic plots directly in your browser.

Data Directory (data/)

This project utilizes core relational datasets evaluating response metrics and environmental covariates:
AMR_2024.12.09.csv: Raw observational field dataset containing sample IDs, lake codes, and target antimicrobial resistance metrics across study lakes.
rf_dat.csv: Processed matrix of environmental, landscape, and climatic covariates configured for Random Forest modeling environments.

Spatial Vector Data

Spatial boundary layers for spatial masking and figure plotting:
vi_outline.shp: Polygon shapefile outlining Vancouver Island (includes associated .shx, .dbf, .prj, and .cpg files).

Spatial Raster Data — Hosted on Zenodo

Due to repository size constraints (>100 MB), high-resolution spatial predictor rasters are archived permanently on Zenodo (DOI: 10.5281/zenodo.21476186):
d2_lake.tif: Distance-to-lake landscape raster.
d2_ancient.tif: Distance-to-ancient-landscape-feature raster.
spp3_cvr.tif: Vegetation species cover raster.
BC/800m/Normal_1991_2020/NFFD09.tif: Normal number of frost-free days (September) climate raster.

To clone and execute this pipeline locally, open R/RStudio and ensure your local environment contains the following dependencies:

# Required Packages for Execution
install.packages(c("MixRF", "randomForest", "caret", "dplyr", "tidyverse", "Hmisc", "ranger", "car", "sp", "sf", "gstat", "ggplot2", "terra", "raster", "patchwork"))

Note: Download the spatial raster archive from Zenodo and extract to your project root prior to running the R Markdown script.

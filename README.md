# InVEST_surrogate

This repository contains code and data for developing a deep learning-based surrogate model of selected [InVEST](https://naturalcapitalproject.stanford.edu/software/invest) modules. The surrogate aims to replicate InVEST outputs efficiently for spatial optimization, especially in green infrastructure planning. The work is WIP.

## 1 Contents

- `Rasters`: Geospatial input files. These are clipped into uniform square samples for training.
- `Sample`: Shapefile defining sample boundaries across the region; used to clip raster inputs.
- `InVEST_Model`: Tabular inputs and workplace for selected InVEST modules—Habitat Quality, Urban Cooling, and Urban Nature Access. Tabular inputs are constant across all samples.
- `Prosd`: Processed tensors (torch inputs) clipped from rasters, saved for model training and InVEST calculation.
- `Normal`: Normalization parameters used for standardizing model inputs.
- `Results`: Ground truth outputs from InVEST simulations, used as training targets for surrogate models.
- `StudySite`: Data and configuration for running GI optimization on a selected case site.

## 2 Code Scripts

- `CNN_InV_01`: Clips raster data using the `Sample` shapefile and saves torch inputs in `Prosd`.
- `CNN_InV_02`: Runs InVEST models and saves outputs in `Results`.
- `CNN_InV_03`: Validates data, defines surrogate model architectures, and trains the models.
- `CNN_InV_04`: Evaluates trained model performance.
- `CNN_InV_05`: Applies surrogate and InVEST models to optimization on the case site and compares results.

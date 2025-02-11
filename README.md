# 2025-hex-assay-analysis

[![run with conda](https://img.shields.io/badge/run%20with-conda-3EB049?labelColor=000000&logo=anaconda)](https://docs.conda.io/projects/miniconda/en/latest/)

## Purpose

This repo contains analysis notebooks for the beta-hexosaminidase degranulation assay and lactate dehydrogenase (LDH) viability assay. Details about these assays and results obtained using them can be found in the Arcadia pub "Compound 48/80 is toxic in HMC1.2 and RBL-2H3 cells" at https://doi.org/10.57844/arcadia-3207-4695.

## Installation and Setup

This repository uses conda to manage software environments and installations. You can find operating system-specific instructions for installing miniconda [here](https://docs.conda.io/projects/miniconda/en/latest/). After installing conda and [mamba](https://mamba.readthedocs.io/en/latest/), run the following command to create the pipeline run environment.

```{bash}
mamba env create -n hex-assay-analysis --file envs/dev.yml
conda activate hex-assay-analysis
```

## Data

Raw data analyzed by these notebooks and found in the associated publication can be found in the [data_files/](./data_files/) folder of this repo. As written, each notebook analyzes one of these files as an example. To analyze a different raw hexosaminidase or LDH assay data file, update the `data_filename` parameter in [analysis_notebooks/hex_assay_analysis_main.ipynb](./analysis_notebooks/hex_assay_analysis_main.ipynb) or [analysis_notebooks/ldh_assay_analysis_main.ipynb](./analysis_notebooks/ldh_assay_analysis_main.ipynb), respectively. To analyze a different processed datafile using [analysis_notebooks/dose_response_analysis.ipynb](./analysis_notebook/dose_response_analysis.ipynb), update the `labeled_datafile_hex` and `labeled_datafile_ldh` parameters.

## Overview

### Directory Structure

* [analysis_notebooks/](./analysis_notebooks/): contains the analysis notebooks used to generate processed data.
* [data_files/](./data_files/): contains the raw data files used to produce processed data in the associated publication.
* [envs/](./envs/): the conda environment used for this repo.
* [sample_manifest/](./sample_manifest/): contains template and example sample manifests that can be updated as needed by users analyzing their own data.

### Methods

> 1. Analyze raw hexosaminidase assay data using [analysis_notebooks/hex_assay_analysis_main.ipynb](./analysis_notebooks/hex_assay_analysis_main.ipynb).
> 2. Analyze raw LDH assay data using [analysis_notebooks/ldh_assay_analysis_main.ipynb](./analysis_notebooks/ldh_assay_analysis_main.ipynb).
> 3. Generate dose response curves using [analysis_notebooks/dose_response_analysis.ipynb](./analysis_notebooks/dose_response_analysis.ipynb), if applicable.

### Compute Specifications

We performed these analyses on a 2023 MacBook Pro with Apple M3 Max Chip and 36 GB of RAM. Given the simplicity of these analyses, we do not expect users to experience difficulty due to insufficient compute.

## Contributing

See how we recognize [feedback and contributions to our code](https://github.com/Arcadia-Science/arcadia-software-handbook/blob/main/guides-and-standards/guide-credit-for-contributions.md).
# pseudobulk-demo

This workflow demonstrates pseudobulk differential testing (DE) analysis of single cell datasets,
clustered and annotated using [Scanpy](https://scanpy.readthedocs.io/en/stable/), as demonstrated
in https://github.com/Mira0507/scanpy-demo. Note that the single cell data was stored both in
Scanpy's [AnnData](https://anndata.readthedocs.io/en/stable/) and Seurat object for flexible 
analysis and data visualization. However, the current workflow is designed to use a Seurat object
as input. 

By default, pseudobulk count matrices are prepared by aggregating read counts per gene per sample. 
DE testing is performed using [DESeq2](https://genomebiology.biomedcentral.com/articles/10.1186/s13059-014-0550-8),
relying on negative binomial distribution. Pseudobulk analysis is more robust when analyzing
differentially expressed genes (DEGs) for single cell dataset by conserving biological variability.
Moreover, pseudobulk analysis enables to remove bias arising from cell number, associated with 
statistical power in null hypothesis testing.

## Repository structure

```
$ tree
.
├── README.md
└── scripts
    ├── helpers.R
    └── pseudobulk_de.Rmd

```

- `helpers.R`: helper functions
- `scripts/pseudobulk_de.Rmd`
    - Single cell metadata
    - Single cell stats by sample, cluster, and experimental condition
    (nCount_RNA, nFeature_RNA, nCells)
    - UMAP by sample, cluster, and experimental condition
    - Absolute and cumulative cell proportion
    - Pseudobulk quality control
        - cluster similarity heatmap
        - PCA
        - Size factors
        - Dispersion-mean plot
        - Differential testing
    - Exploratory plots
        - MA plots
        - P-value distribution
        - [UpSet plots](https://upset.app/)
    - Result tables

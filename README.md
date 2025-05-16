# pseudobulk-demo

This workflow demonstrates pseudobulk differential testing (DE) analysis of single cell datasets,
clustered and annotated using [Scanpy](https://scanpy.readthedocs.io/en/stable/), as demonstrated
in https://github.com/Mira0507/scanpy-demo. Note that the single cell data was stored both in
Scanpy's [AnnData](https://anndata.readthedocs.io/en/stable/) and Seurat object for flexible 
analysis and data visualization. However, the current workflow is designed to use a Seurat object
as input. 

## Repository structure

```
$ tree
.
├── README.md
└── scripts
    ├── helpers.R
    └── pseudobulk_de.Rmd

```



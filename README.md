# Master Regulator Analysis in Papillary Thyroid Cancer

A network-based analysis of gene expression data, asking which transcription factors
drive the shift from healthy thyroid tissue to a tumour phenotype. Final project for
the **Complex Networks** course at the University of Buenos Aires.

RNA-seq samples were taken from the **TCGA** database, using paired tumour and
normal tissue from the same patients, and split by driver mutation (BRAF and RAS).

## The approach

1. **Differential expression** between paired tumour and normal samples, stratified by mutation
2. **Network inference** with ARACNe to reconstruct the gene regulatory network
3. **Master Regulator Analysis** to find transcription factors whose targets are enriched
   in the differential signature, with shadow correction to remove redundant regulators
4. **Community detection** on the resulting network, with modularity examined across resolutions
5. **Functional annotation** via GO and KEGG enrichment on the recovered modules

## What's here

- `Redes complejas - TP final.ipynb` — the analysis (Python: `networkx`, `pandas`, `numpy`, `matplotlib`, `seaborn`)
- `Informe_final.pdf` — the written report
- `Presentaciones/` — final presentation slides
- `Figuras/` — generated figures: PCA, differential expression, MRA results,
  network modularity layouts, GO clusters, and per-regulator ego networks
- `RMA_*.tsv`, `DataDEG_*.tsv` — results tables
- `ARACNe_net.gml`, `NFkB_subgraph.gml` — inferred networks

## Findings, briefly

Several transcription factors came out as candidate master regulators, with partly
distinct sets for BRAF- and RAS-driven tumours. Ego-network and pathway analysis
placed a number of them near NF-κB signalling. The full argument is in the report.

## Notes

Group project, 2018. Exploratory coursework rather than a validated result —
no independent cohort was used, so treat the regulator list as candidates.

# IIR_pipeline

The scripts in this repository correspond to different sections of the manuscript (published in [eLife](https://elifesciences.org/reviewed-preprints/92870)). Required data files can be retrieved from 10.5281/zenodo.8121610 and extracted to the /data folder.

## Part 1 - Inhibitory receptor predictions
Corresponds to Figure 1 of the paper.
1) First all peptide sequences are retrieved from the ensembl database and filtered for those annotated to be protein-coding and containing an ITIM/ITSM sequence anywhere in the protein.
2) The resulting .fasta file is used to predict topologies with [TOPCONS](https://doi.org/10.1093/nar/gkv485).
3) The TOPCONS results are then used to filter out proteins containing an ITIM in the intracellular domain of the protein and annotated with their HGNC gene symbol.
4) Afterwards, we used permutation testing to determine the likelihood of an ITIM being present by chance in the intracellular domain of the proteins.
5) Fasta files were then exported for the proteins passing the likelihood filter, and three-dimensional structure was determined using AlphaFold.
6) PDB files could then be loaded again and proteins were filtered based on the average confidence score of the amino acids included in the ITIM domain.
7) Remaining proteins were then exported as novel putative inhibitory receptors.
   
## Part 2 - Functional categorization
Corresponds to Figure 2 of the paper.

## Part 3 - Tumour infiltrating T cells
Corresponds to Figure 3 of the paper.

## Figures and output
Figures and output tables used in the manuscript were generated using output_figures.Rmd from processed files generated during previous steps of the pipeline.




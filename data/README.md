# Public data included in this repository

`03_matched_pairs_16x3.csv` is the fixed 16 × 3 matched-comparator table used by the downstream matched-comparator analyses. It contains public NCBI BioSample and assembly accessions, MIC values, matching ranks, and derived chromosomal relatedness/distance values.

Raw genome assemblies are not stored in Git. Notebook 08 retrieves the public NCBI assemblies from their accessions, and the later notebooks regenerate the large chromosome/unitig intermediate files.

Notebook 01 reuses processed inputs from the preceding `Genome_MIC_AMR_Emergence` analysis. To rerun Notebook 01 exactly, set `GENOME_MIC_AMR_PROJECT_ROOT` to that project/repository location.

# Public data included in this repository

`03_matched_pairs_16x3.csv` is the fixed 16 × 3 matched-comparator table used by the downstream matched-comparator analyses. It contains public NCBI BioSample and assembly accessions, MIC values, matching ranks, and derived chromosomal relatedness/distance values.

Raw genome assemblies are not stored in Git. Notebook 08 retrieves the public NCBI assemblies from their accessions, and the later notebooks regenerate the large chromosome/unitig intermediate files.

Notebook 01 reuses processed inputs from the preceding `Genome_MIC_AMR_Emergence` analysis. To rerun Notebook 01 exactly, set `GENOME_MIC_AMR_PROJECT_ROOT` to that project/repository location.

Supplementary_Table_S2a_Mapped_Subwindows.csv contains the supported MG1655-mapped subwindows reported in Supplementary Table S2a. MG1655 coordinates are 1-based and inclusive.

Supplementary_Table_S2b_Noncoordinate_Groups.csv contains the supported UNMAPPED and MULTIMAPPED sequence groups reported in Supplementary Table S2b.

Supplementary_Table_S2c_Higher_MIC_Patterns.csv contains the individually significant higher-MIC sequence patterns P7319 and P2846 reported in Supplementary Table S2c.

These three files provide the numerical results reported in Supplementary Table S2 of Online Resource 1.

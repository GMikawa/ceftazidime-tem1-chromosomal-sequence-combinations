# Chromosomal sequence combinations associated with substantially elevated ceftazidime MIC in *blaTEM-1*-only *Escherichia coli*

This repository contains the public analysis and figure-generation code supporting the manuscript. The analysis uses 176 *blaTEM-1*-only *E. coli* pathogens with exact ceftazidime MIC measurements and corresponding public NCBI genome assemblies.

## Repository contents

- `03_Notebooks/04_Genome_Comparison/` — final notebooks required for the reported cohort, matching, chromosome/unitig, association, localisation, and matched-comparator analyses.
- `06_Manuscript/Figure_Notebooks/` — final code used for manuscript Figures 2–4 and annotation of the three BH-significant sequence patterns.
- `06_Manuscript/Figures/` — final manuscript Figures 1–4.
- `data/03_matched_pairs_16x3.csv` — fixed matched-comparator table used downstream.

Exploratory, failed, duplicated, and superseded notebooks are intentionally excluded. Raw NCBI assemblies and large generated unitig matrices are also excluded from Git.

## Analysis order

1. `01_TEM1_High_MIC_Chromosomal_Clustering.ipynb` — defines the 176-pathogen cohort, 16 high-MIC pathogens, and high-MIC chromosomal-similarity test.
2. `02_TEM1_High_MIC_Matched_Controls.ipynb` — constructs the high-MIC-to-comparison chromosomal-distance table.
3. `03_TEM1_High_MIC_Matched_Comparator_Selection.ipynb` — applies the fixed 3-comparator matching rule.
4. `08_Whole_Chromosomal_Sequence_Comparison_Feasibility_UPDATED.ipynb` — verifies assembly mapping, retrieves the 176 public assemblies, and performs sequence QC.
5. `09_Platon_Chromosome_Plasmid_Separation_176.ipynb` — separates chromosome and plasmid sequence using Platon.
6. `10_Whole_Chromosome_Unitig_Representation.ipynb` — constructs the variable chromosome unitig representation (k = 31).
7. `11_Unitig_Pattern_Consolidation_and_High_MIC_Exclusivity.ipynb` — consolidates identical unitig presence/absence patterns.
8. `17_Full_Chromosomal_Unitig_Pattern_Association_with_Continuous_Ceftazidime_MIC.ipynb` — tests all unique patterns with the K-adjusted association model.
9. `18_Collective_Whole_Chromosome_Sequence_Association_with_Ceftazidime_MIC.ipynb` — estimates the whole-chromosome unitig variance fraction and permutation p value.
10. `19_Broad_Unitig_Ablation_of_Collective_Whole_Chromosome_Association.ipynb` — assigns unitigs to broad mapped/non-coordinate groups and calculates observed ablation effects.
11. `20_Matched_Random_Ablation_Benchmark.ipynb` — evaluates broad groups against matched random removals.
12. `21_Mapped_Priority_Window_Subwindow_Ablation.ipynb` — refines retained mapped windows into supported subwindows.
13. `22_Unmapped_Multimapped_Carrier_Pattern_Refinement.ipynb` — refines retained non-coordinate groups by carrier-pattern clustering.
14. `24_Exact_Mapped_Sequence_State_Visualization.ipynb` — constructs exact sequence states for the supported mapped subwindows.
15. `25_High_MIC_Matched_Comparator_Locus_Distribution.ipynb` — performs the final matched-comparator mapped-subwindow comparison.

The Figure 2–4 notebooks should be run after their required analysis outputs have been generated. `Figure03_Significant_Pattern_Annotation.ipynb` uses outputs from Notebooks 10, 11, 17, and 19.

## Paths

The public notebooks do not contain personal Google Drive paths. By default they locate the repository root by searching upward for this `README.md`. To use another location, set:

```bash
export CEFTAZIDIME_PROJECT_ROOT=/path/to/this/repository
```

Notebook 01 and part of Notebook 08 reuse processed inputs from the preceding `Genome_MIC_AMR_Emergence` project. Set:

```bash
export GENOME_MIC_AMR_PROJECT_ROOT=/path/to/Genome_MIC_AMR_Emergence
```

or place that project under `external/Genome_MIC_AMR_Emergence/`.

## Software

Python packages are listed in `requirements.txt`. The workflow also uses external command-line/software resources where indicated in the notebooks, including NCBI Datasets, Platon, unitig-caller, Bowtie2, BLASTN, and KBase/VirSorter2 for the reported sequence annotation.

## Data availability

The underlying genome assemblies and BioSample records are public NCBI records identified by accession. Raw assemblies are deliberately not duplicated in this Git repository. Large generated intermediate files are reproducible from the notebooks and are excluded by .gitignore.

Notebook 01 and part of Notebook 08 additionally require processed inputs from the preceding Genome_MIC_AMR_Emergence analysis, as described under Paths above.
## Public-release sanitisation

Notebook outputs/execution history and local Google Drive paths were removed from the public copies. The scientific analysis logic and fixed analysis settings were retained. Final PNG files were re-saved without embedded PNG metadata; their pixel content was not altered.

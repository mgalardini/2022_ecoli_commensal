# Snakemake workflow for wg-GWAS on _E. coli_ commensal and BSI

Snakemake pipeline to reproduce the wg-GWAS analysis on the genetic determinants of *E. coli* bloodstream infections (BSI) and commensal isolates. Users wishing to replicate this study should place the data containig the phenotype and covariates within the `data/` directory. Further details can be found in the [preprint](https://www.biorxiv.org/content/10.1101/2022.12.31.522367v1).

## Input genomes
The input assemblies can be found under the following bioproject accessions:

| Phenotype | Bioproject accession |
| ------------- | ------------- |
| BSI | [PRJEB39260](https://www.ebi.ac.uk/ena/browser/view/PRJEB39260), [PRJEB35745](https://www.ebi.ac.uk/ena/browser/view/PRJEB39260) |
| Commensal | [PRJEB38489](https://www.ebi.ac.uk/ena/browser/view/PRJEB38489), [PRJEB44819](https://www.ebi.ac.uk/ena/browser/view/PRJEB44819), [PRJEB44872](https://www.ebi.ac.uk/ena/browser/view/PRJEB44872), [PRJEB39252](https://www.ebi.ac.uk/ena/browser/view/PRJEB39252), [PRJEB55584](https://www.ncbi.nlm.nih.gov/bioproject/?term=PRJEB55584) |

The fasta files should be placed inside the `data/fastas` directory, and the annotated gff files in the `data/gffs` directory.

## Usage
To make a dry run of the analyis:
```
snakemake --use-conda --cores 36 -n -p
```
Snakemake will install the appropriate packages for each step as conda environments when running it without the `-n` flag.

A symbolic link to a directory containing the eggnog-mapper database should be placed in `data/eggnog-mapper`, as well as one to the unzipped fasta file from uniref50 (`data/uniref50.fasta`).

## Author
Judit Burgaya (BurgayaVentura.Judit@mh-hannover.de)


The pipeline was in great part based on this [workflow](https://github.com/microbial-pangenomes-lab/2021_ecoli_pathogenicity) from our [lab](https://github.com/microbial-pangenomes-lab), previously used in:

Denamur E, Condamine B, Esposito-Farèse M, Royer G, Clermont O, et al. (2022) Genome wide association study of Escherichia coli bloodstream infection isolates identifies genetic determinants for the portal of entry but not fatal outcome. PLOS Genetics 18(3): e1010112. https://doi.org/10.1371/journal.pgen.1010112


# Pfrender Lab
## Overview
Projects completed as an undergraduate member of Dr. Michael Pfrender's Evolutionary/Ecological Genomics Lab at the University of Notre Dame. 

## Sequence Diversity & Genetic Barcodes (n_diverse_sequences.R)
### Description
One use of this code is estimating the variation in genetic barcodes using sequences from a single species. The code reads in a .fasta or .afa file of sequences, aligns the sequences, and can perform any combination of the following:
- Write a file of aligned sequences
- Produce a phylogenic tree of the sequences
- Write a file containing the names of the 'n' most diverse sequences (use-specified)

### Libraries and versions:
- getopt: version 1.20.3  
- BiocManager: version 1.30.10
- seqinr: version 3.6-1
- ape: version 5.3
- DECIPHER: version 2.14.0

### Usage
Command line usage:
```sh
 Rscript n_seq_script.R -i <input_file_name> 
```
Flags:
1. -h ...Help – display all flags
2. -v ...Version – display version of script
3. -i <file_name>...Input – required argument to specify input .fasta or .afa file
4. -t ...Tree – produces .jpeg phylogenic tree
5. -a ...Aligned - writes file of aligned sequences
6. -d ...Diversity - writes file with the names of the 'n' most diverse sequences
7. -n <integer_value>...Num - number of sequences desired for diversity methods. The default is 1.
8. -p <string_for_file_name>...Project - all files created will start with '<argument_user_entered>...'

### Cite
michalekb. 2020. “Michalekb/N-Most-Diverse-Sequences: N-Most-Diverse-Sequences,” April. https://doi.org/10.5281/ZENODO.3754619.

## RNAseq Analysis: Daphnia Edition
### Description
The R scripts in the GO and GSEA folders were written to assist Elizabeth Brooks in her research and dissertation. 
Elizabeth's research involves using short paired-end RNAseq reads to investigate how various Daphnia (water fleas) genotypes respond and deal with UV radiation. For example, some daphnia produce melanin, leading to pigmentation and protection against UV waves. Others use various DNA repair methods for which the genes and pathways activated by UV light are not well understood. My work in the Pfrender Lab involved a statistical investigation into the transcriptome changes in response to UV light with particular attention to DNA repair pathways across a mixture of UV tolerant and UV non-tolerant genotypes.  

Components of project:
- <ins>Gene Ontology Analysis (GO):</ins>
- <ins>Gene Set Enrichment Analysis (GSEA):</ins>

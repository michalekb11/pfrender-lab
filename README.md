# Pfrender Lab
## Overview
Projects completed as an undergraduate member of Dr. Michael Pfrender's Evolutionary/Ecological Genomics Lab at the University of Notre Dame. 

## Sequence Diversity & Genetic Barcodes (n_seq_script.R)
### Description
One use of this code is estimating the variation in genetic barcodes using sequences from a single species. The code reads in a .fasta or .afa file of sequences, aligns the sequences, and can perform any combination of the following:
- Write a file of aligned sequences
- Produce a phylogenic tree of the sequences
- Write a file containing the names of the 'n' most diverse sequences (user-specified)

### Libraries and versions (R):
- getopt: version 1.20.3  
- BiocManager: version 1.30.10
- seqinr: version 3.6-1
- ape: version 5.3
- DECIPHER: version 2.14.0

### Input Data
A .fasta or .afa file containing DNA/RNA sequences.

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
Elizabeth's research involves using short paired-end RNAseq reads to investigate how various Daphnia (water fleas) genotypes respond and deal with UV radiation. For example, some daphnia produce melanin, leading to pigmentation and protection against UV waves. Others use various DNA repair methods for which the genes and pathways activated by UV light are not well understood. My work in the Pfrender Lab involved a statistical investigation into the transcriptome changes in response to UV light with particular attention to DNA repair pathways across a mixture of UV tolerant and UV non-tolerant Daphnia genotypes.  

Project Components:
- <ins>Gene Ontology Analysis (GO):</ins> GO represents a database of gene groups. Each GO term contains a set of genes known to be involved in that respective process/pathway/function. The GO terms themselves are categorized as either a Biological Process, Cellular Component, or Molecular Function. Given a set of differentially expressed genes, it is possible to determine which GO terms, if any, are significantly upregulated or downregulated between the treatment groups. Here, I accomplish this task with the Daphnia UV data.
- <ins>Gene Set Enrichment Analysis (GSEA):</ins> GSEA is similar to GO in that an expression matrix can be used to determine whether a pre-defined set of genes shows statistically significant differences between two treatment groups. However, this method is not limited to GO terms but rather can include gene sets from other sources (KEGG pathways, researcher-defined gene sets, etc.).  
  - General GSEA procedure: Develop linear model for each gene to calculate gene-wise test statistics (linear model allows for testing multiple contrasts per gene). Calculate a gene set test statistic using t tests or Wilcoxon rank sum tests. 

### Input Data (GSEA)
1. A .csv containing a matrix of gene expression (or log expression) data with a column name row representing the replicates. 
2. A factor grouping .csv file containing a column for the replicates (the column names of the expression file) and a column for each contrast (Ex: Treatment = {UV, VIS}, Tolerance = {Tol, NTol})

### Usage (GSEA)
Command line usage:
```sh
Rscript geneSetTesting_allContrastsOlympics_camera.r <expression_file> <factor_grouping_file>
```

### Example Results
<p align="center">
<img width="674" alt="Screen Shot 2022-07-26 at 12 59 18 PM" src="https://user-images.githubusercontent.com/109704770/181066338-1a86d74d-51a4-44b4-8e75-dc33cecf24b6.png">
</p>

# Frodo
Fungal rRna Operon Database using Ont sequencing
## Manual of Nanopore Sequencing of Full rRNA Operon in Mycobiome Analysis

High-throughput sequencing targeted ITS1/ITS2 region has greatly improved our understanding on fungal diversity, but still suffer from limited taxonomic and phylogenetic resolution for species discrimination based on short reads (\<500bp). We established a pipeline covering almost complete fungal rRNA operon gene, spanning the entire ITS region and the SSU and LSU region to provide greater taxonomic resolution.

### 1. Amplification of the full-length rRNA operons (~ 5.5kb)

Amplify the full ribosomal operon sequences with the PCR primer pair SR1R(F), LR11(R) and/or SR1R(F), LR14(R). Product purification using Ampure XP magnetic beads.We prefer the former primer pair. 

To improve amplification fidelity, can use high-fidelity PCR polymerase, and diluted DNA templates for multiple parallel PCR reactions simultaneously.

### MinION library construction and Nanopore sequencing

Prepare the sequencing libraries of operon sequences using the Native barcoding genomic DNA protocol with EXP-NBD104, EXP-NBD114 and SQK-LSK109 kits (Oxford Nanopore Technologies). 

### 3. Nanopore sequencing Data analysis

After base-calling, Qcat ([https://github.com/nanoporetech/qcat](https://github.com/nanoporetech/qcat)) is used to demultiplex raw reads and trim adaptors. 

Then, filter FASTQ sequences by bioawk ([https://github.com/lh3/bioawk](https://github.com/lh3/bioawk)) with lengths of 2,000 bp to 9,000bp (4000bp to 9000bp strictly) for the full fungal rRNA operon and converse to FASTA format.

RDP Classifier ([https://github.com/rdpstaff/classifier](https://github.com/rdpstaff/classifier)) classify the filtered sequences with training set based on our FRODO database and the default confidence of 0.8 for downstream analysis of mycobiome diversity.



The reference database FRODO (Fungal rRNA Operon Database for ONT-sequences) was collected a total of 9,072 fungal genome sequences from NCBI, JGI, FungiDB, Ensembl Fungi and Broad Institute to extract complete rRNA operon sequences. After de-duplication and identify credible operons, 8 phyla, 41 classes, 109 orders, 256 families, 524 genera and 1,116 species are included in FRODO database. 

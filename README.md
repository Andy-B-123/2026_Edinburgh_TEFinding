# Data Sources for Reproducing Read Mappings

## Large TE Insertion Associated with Vip3Aa Resistance in *Helicoverpa armigera*

This repository documents the data sources and analysis context needed to reproduce read mappings for a large transposable element (TE) insertion associated with Vip3Aa resistance in *Helicoverpa armigera*.

## Preprint

BioRxiv:
https://www.biorxiv.org/content/10.64898/2026.04.06.716841v1

## Original Sequencing Data

| Sample         | SRA accession                                      |
| -------------- | -------------------------------------------------- |
| F0 Resistant   | https://www.ncbi.nlm.nih.gov/sra/?term=SRR36217574 |
| F0 Susceptible | https://www.ncbi.nlm.nih.gov/sra/?term=SRR36217575 |

## Informative-Cross Samples

Eight samples from a female and male informative cross are provided below. These samples should be used to test whether the disruption variant event can be identified correctly and whether the genotype can be called accurately in each individual.

| Run         | Library name |
| ----------- | ------------ |
| SRR36217597 | 17xFIC2-P_1  |
| SRR36217596 | 17xFIC2-P_2  |
| SRR36217575 | 17xGR-GP_1   |
| SRR36217574 | 17xGR-GP_2   |
| SRR36217573 | GRx17-GP_1   |
| SRR36217572 | GRx17-GP_2   |
| SRR36217547 | MIC2x17-P_1  |
| SRR36217546 | MIC2x17-P_2  |

The goal is to correctly identify both:

1. The disruption variant event, and
2. The genotype of the variant in all eight samples.

Across these eight samples, the expected genotype classes are:

| Expected class                 | Number of individuals |
| ------------------------------ | --------------------: |
| Homozygous for the insertion   |                     4 |
| Heterozygous for the insertion |                     2 |
| No insertion variant           |                     2 |

A successful analysis should correctly recover the variant event and assign the correct genotype class for all eight samples.

## Reference Genome

Reference assembly: [GCA_040954515.1](https://www.ncbi.nlm.nih.gov/datasets/genome/GCA_040954515.1/)

## Mapping Tools

The following mappers were used:

* BWA-MEM
* Minimap2 with `-x sr`

## Variant Callers

The following variant callers were tested:

* BCFtools
* FreeBayes
* GATK
* BBMap CallVariants

## Structural Variant and TE Tools

The following SV and TE-focused tools were tested:

* Smoove
* MindTheGap
* SCRAMBLE
* TEF

## Challenge

Please identify the large transposable element insertion at:

```text
CM082456.1:4822339-4822347
```

The insertion has a 9 bp target site duplication (TSD):

```text
GGA-ACA-AAT
```

GATK came closest to identifying the event, as it calls an insertion at this site. However, it only reports the variant as heterozygous. Across the eight called samples, GATK reliably identified a heterozygous variant at this position in only about half of them.

The expected call should be a **homozygous insertion** in the relevant individuals.

If you can provide:

1. A screenshot showing the insertion in the alignment,
2. Reproducible steps for identifying or calling the insertion, and
3. Correct genotypes for all eight informative-cross samples,

then dinner is on me!

## Alignment Screenshot

Screenshot of the alignment indicating the insertion:

<!-- Add screenshot here -->

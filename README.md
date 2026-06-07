# Data Sources for Reproducing Read Mappings

## Large TE Insertion Associated with Vip3Aa Resistance in *Helicoverpa armigera*

This repository documents the data sources and analysis context needed to reproduce read mappings for a large transposable element (TE) insertion associated with Vip3Aa resistance in *Helicoverpa armigera*.

## Preprint

BioRxiv:
https://www.biorxiv.org/content/10.64898/2026.04.06.716841v1

## Sequencing Data

| Sample         | SRA accession                                      |
| -------------- | -------------------------------------------------- |
| F0 Resistant   | https://www.ncbi.nlm.nih.gov/sra/?term=SRR36217574 |
| F0 Susceptible | https://www.ncbi.nlm.nih.gov/sra/?term=SRR36217575 |

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

The expected call should be a **homozygous insertion**.

If you can provide:

1. A screenshot showing the insertion in the alignment, and
2. Reproducible steps for identifying or calling the insertion,

then dinner is on me!

## Alignment Screenshot

Screenshot of the alignment indicating the insertion:

<!-- Add screenshot here -->

Data sources and descriptions for reproducing read mappings for the large TE insertion for VIp3Aa resistance in Helicoverpa armigera

BIoArxiv: https://www.biorxiv.org/content/10.64898/2026.04.06.716841v1

F0 Resistant - https://www.ncbi.nlm.nih.gov/sra/?term=SRR36217574
F0 Susceptible - https://www.ncbi.nlm.nih.gov/sra/?term=SRR36217575

Reference - [GCA_040954515.1](https://www.ncbi.nlm.nih.gov/datasets/genome/GCA_040954515.1/)

Mapper used - BWA-Mem, Minimap (-x sr)

Callers used - BCFtools, Freebayes, GatK, BBMap's CallVariants
SV tools used - Smoove, MindTheGap, SCRAMBLE, TEF

Challenge:
Please identify the large transposable element insertion at CM082456.1:4822339-4822347. It has a 9bp TSD of GGA-ACA-AAT.
GatK got closest (calls insertion) but it only ever calls this a heterozygous variant. Out of the 8 called sampels it only reliably called a heterozygous variant here in about half the samples. 

It should be a homozygous call of an insertion. If you can provide a screenshot + reproducible steps I will buy you dinner!

Screenshot of alignment indicating insertion:



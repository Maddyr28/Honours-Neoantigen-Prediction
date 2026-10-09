Honours Neoantigen Prediction Overview


This repository contains the bioinformatic code used for neoantigen prediction in the murine ER+ breast cancer cell line SSM3, as part of an Honours thesis project (2026).

The pipeline identifies tumour-specific somatic variants from murine whole genome sequencing data, integrates RNA-seq expression data, and uses pVACseq to predict and prioritise candidate neoantigen peptides for potential use as personalised cancer vaccine targets.

Data
* SSM3 WGS: SRR2142076 (SRA)
* TAC239 germline WGS: SRR2141680 (SRA)
* SSM3 RNA-seq: SRR29245256 (GEO: GSE268752)
* Reference genome: Mus musculus GRCm39 (Ensembl release 115)

Pipeline Overview
1. Quality control — fastp
2. WGS alignment — BWA-MEM
3. Duplicate marking — GATK MarkDuplicates
4. Somatic variant calling — GATK Mutect2
5. Variant annotation — Ensembl VEP (release 115)
6. RNA-seq alignment — STAR (two-pass mode)
7. Expression quantification — StringTie
8. RNA readcount generation — bam-readcount
9. VCF expression annotation — VAtools
10. Neoantigen prediction — pVACseq (v5.2.0)

Key tools and versions used:
* fastp v1.3.5
* BWA v0.7.19
* SAMtools v1.20
* GATK v4.3.0.0
* Ensembl VEP v115
* STAR v2.2.11b
* StringTie v2.2.3
* bam-readcount v1.0.1
* vatools v5.2.0
* pVACtools v5.2.0
* Python v3.9.21

Usage
All code is documented in Honours_Neoantigen_Prediction.Rmd. Commands are written for a Linux HPC environment using conda for environment management.

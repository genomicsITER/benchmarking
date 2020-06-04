# Benchmarking
Benchmarking of WGS and WES workflows from NGS reference data and reference samples sequenced at ITER 

## Table of contents

* [Description](#description)
* [Comparison](#comparison)
* [Funding](#funding)

---

## Description

Bioinformatics benchmarking is essential to provide guidance for improving the variant calling process and define standards and performance metrics. We aimed to assess the performance of our current whole-genome (WGS) and whole-exome (WES) sequencing and bioinformatic workflows for detecting single nucleotide variants (SNVs) and small insertion and deletion (indels) in human samples.

For this purpose, we used the Genome in a Bottle (GIAB) NA12878/HG001 pilot sample provided by the PrecisionFDA. This sample has been studied extensively and is used as a reference for benchmarking. we aimed to perform our experiment in two different comparisons: one comparison for whole genome sequences and another comparison for whole-exome sequences.

---

## Comparison

Following the guidelines of the Truth and Consistency precisionFDA challenges we used hap.py and vcfeval tools for comparing our results with the reference VCF sample. These tools assess three different metrics: recall, precision and F-measure.

---

## Funding

Ministerio de Ciencia e Innovación (RTC-2017-6471-1; AEI/FEDER, UE); ITER agreement OA17/008; ECIT-ITER CGIEU0000219140; Ministerio de Educación y Formación Profesional (A.D.U.; FPU16/01435).

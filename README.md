# Benchmarking
Benchmarking of WGS and WES workflows from NGS reference data and reference samples sequenced at ITER 

![](https://github.com/genomicsITER/benchmarking/blob/master/images/funding_1.png)

## Table of contents

* [Description](#description)
* [Comparison](#comparison)
* [Conclusions](#conclusions)
* [Funding](#funding)

---

## Description

Bioinformatics benchmarking is essential to provide guidance for improving the variant calling process and define standards and performance metrics. To achieve this goal, several public-private-academic organisations have arisen in the last few years. One of them is the Genome in a Bottle ([GIAB](https://jimb.stanford.edu/giab)) Consortium, hosted by National Institute of Standards and Technology ([NIST](https://www.nist.gov/)). It provides reference materials, standards and methods to perform translation of whole human genome sequencing to clinical practice. GIAB follows the Global Alliance for Genomics and Health (GA4GH) Benchmarking Team recommendations to standardise performance metrics and tools that enables to accomplish the previous goal. Also, [PrecisionFDA](https://precision.fda.gov/) is a platform from Food and Drug Administration (FDA) involved in the analysis of biological datasets in order to advance precision medicine.

We aimed to assess the performance of our current whole-genome (WGS) and whole-exome (WES) sequencing and bioinformatic workflows for detecting single nucleotide variants (SNVs) and small insertion and deletion (indels) in human samples. For this purpose, we used two Genome in a Bottle reference samples:

* NA12878/HG001: This sample belongs to a well-known multigenerational family from Utah in the US.
* NA24385/HG002: This sample belongs to the son member of an Ashkenazi Jews trio.

These sample has been studied extensively and are used as a reference for benchmarking.

---

## Comparison

Following the guidelines of the Truth and Consistency precisionFDA challenges we used [hap.py](https://github.com/Illumina/hap.py) and [vcfeval](https://github.com/RealTimeGenomics/rtg-tools) tools for comparing our results with the reference VCF sample. These tools assess three different metrics: recall, precision and F-measure.

* Recall: also known as sensitivity, defined as the percentage of real variants that we were able to identify.
* Precision: defined as the percentage of variants we called that are actually real.
* F-measure: defined as the harmonic mean of the precision and recall.

<p align="center">
  <img src="https://github.com/genomicsITER/benchmarking/blob/master/images/comparison.png">
</p>

We aimed to perform our experiment in two different comparisons: one comparison for whole genome sequences and another comparison for whole-exome sequences.

<p align="center">
    <a href="https://github.com/genomicsITER/benchmarking/tree/master/WGS" title="Go to WGS">
      <img src="https://github.com/genomicsITER/benchmarking/blob/master/images/WGS.png">
    </a> 
    <a href="https://github.com/genomicsITER/benchmarking/tree/master/WES" title="Go to WES">
      <img src="https://github.com/genomicsITER/benchmarking/blob/master/images/WES.png">
    </a>
</p>

---

## Conclusions

We have developed and tested a custom pipeline to conduct WGS and WES-based benchmarking to ensure reproducibility. These results support that our current procedures and workflows are reliable, albeit a fine-grained study of inaccuracies is underway.

---

## Funding

Ministerio de Ciencia e Innovación (RTC-2017-6471-1; AEI/FEDER, UE); ITER agreement OA17/008; ECIT-ITER CGIEU0000219140; Ministerio de Educación y Formación Profesional (A.D.U.; FPU16/01435).

![](https://github.com/genomicsITER/benchmarking/blob/master/images/funding_2.png)


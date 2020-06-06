# Whole genome sequencing

For whole genome sequencing benchmarking we performed two PrecisionFDA challenges that took place in 2016: [Consistency](https://precision.fda.gov/challenges/consistency) and [Truth](https://precision.fda.gov/challenges/truth) Challenges. The goal of these two challenges is to improve quality standards in order to achieve more accurate and consistent results in the context of genetic tests. The main structure of both challenges is very similar but, there are a few changing details.

### Consistency Challenge

First, for Consistency Challenge two datasets from HG001 pilot sample were provided. Both samples were sequenced on a HiSeq X with the same conditions but in differents sequencing centers (Garvan Institute of Medical Research and Human Longevity, Inc.). The main purpose is to study reproducibility between different datasets of the same sample and analyse if the input affects the accuracy of results. This accuracy is determined in terms of recall, precision and F-measure. You can find a more detailed scheme of this challenge on the next figure.

<p align="center">
  <img src="https://github.com/genomicsITER/benchmarking/blob/master/WGS/images/Consistency_Challenge_workflow.png" width="70%">
</p>

### Truth Challenge

As already stated, both challenges are very similar. However, this challenge improves results evaluation considering SNP and indels separately. Normally, SNPs calling is easier than indel calling, so, reporting separate statistics for SNPs and indels can be advantageous for a better understanding of results. Also, NA24385/HG002 reference sample is added to provided datasets. This new sample allows to avoid variant calling overfitting for a single reference sample. You can find a more detailed scheme of this challenge on the next figure.

<p align="center">
  <img src="https://github.com/genomicsITER/benchmarking/blob/master/WGS/images/Truth_Challenge_workflow.png" width="45%">
</p>

## Material and methods

Once we downloaded datasets we ran our variant calling pipeline. In short, WGS reads were aligned to GRCh37 reference with BWA-MEM v0.7.15-r1140. BAM files were processed with SAMtools v1.3 and Picard v2.10.10, and SNVs and indels were identified with the HaplotypeCaller following the Genome Analysis Toolkit Best Practices workflow recommendations for germline variant calling (GATK). A complete workflow is shown below.

<p align="center">
  <img src="https://github.com/genomicsITER/benchmarking/blob/master/WGS/images/WGS_workflow.png">
</p>

## Results

For the first challenge we called the same variants by rerunning our pipeline with the same input, so, we concluded that our pipeline is reproducible. Focusing on accuracy results, a relatively high performance was observed according to recall, precision and F-measure metrics from the benchmarking of both challenges. Remarkably, both indel recall and F-measure values are higher in our Truth Challenge results.

<p align="center">
  <img src="https://github.com/genomicsITER/benchmarking/blob/master/WGS/images/ConsistencyChallenge_results.png" width="45%">
  <img src="https://github.com/genomicsITER/benchmarking/blob/master/WGS/images/TruthChallenge_results.png" width="47.5%">
</p>

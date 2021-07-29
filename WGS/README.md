# Whole genome sequencing 

For whole genome sequencing benchmarking we performed three PrecisionFDA challenges: [Consistency](https://precision.fda.gov/challenges/consistency) and [Truth](https://precision.fda.gov/challenges/truth) Challenges in 2016, and [Truth Challenge V2](https://precision.fda.gov/challenges/10) in 2020. The goal of these three challenges is to improve quality standards in order to achieve more accurate and consistent results in the context of genetic tests. The main structure of the challenges is very similar but, there are a few changing details.

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

### Truth Challenge V2

Previous benchmarks were limited to “easier-to-map” regions of the genome. However, new long and linked read technologies along with new bioinformatics pipelines have enabled the characterization of increasingly challenging regions of the genome. In January 2020, the PrecisionFDA project announced the Truth Challenge V2. This challenge assessed variant calling pipeline performance with a focus on difficult-to-map regions, segmental duplications, and Major Histocompatibility Complex (MHC) using three Genome in a Bottle human genome benchmarks (HG002, HG003 and HG004; the son, father and mother of the Ashkenazi trio, respectively). You can find a more detailed scheme of this challenge on the next figure.

<p align="center">
  <img src="https://github.com/genomicsITER/benchmarking/blob/master/WGS/images/TruthChallenge-V2_workflow.png" width="45%">
</p>

## Material and methods

Once we downloaded datasets we ran our variant calling pipeline. In short, WGS reads were aligned to GRCh37 reference with BWA-MEM v0.7.15-r1140. BAM files were processed with SAMtools v1.3 and Picard v2.10.10, and SNVs and indels were identified with the HaplotypeCaller following the Genome Analysis Toolkit Best Practices workflow recommendations for germline variant calling (GATK). A complete workflow is shown below.

<p align="center">
  <img src="https://github.com/genomicsITER/benchmarking/blob/master/WGS/images/WGS_workflow.png">
</p>

For Truth Challenge V2, PrecisionFDA provided FASTQ files from three different technologies, Illumina, PacBio and ONT. So, we performed a different approach for this challenge. Illumina dataset were processed as the previous challenges, but, GRCh38 reference genome was used instead of GRCh37. For PacBio and ONT datasets we used Minimap2 v2.17 for alignment and Longshot v0.4.1 for variant calling.

## Results

For the first challenge we called the same variants by rerunning our pipeline with the same input, so, we concluded that our pipeline is reproducible. Focusing on accuracy results, a relatively high performance was observed according to recall, precision and F-measure metrics from the benchmarking of first two challenges. We compared our results with those from other top-ranked pipelines for each challenge. Our ranking on each challenge is shown in white numbers (out of nineteen and twenty-nine participants in the Consistency and Truth Challenges, respectively). We found that our values are not the highest in the Consistency Challenge but, even though, they are still good enough. In the Truth Challenge comparison, both the recall and F-measure metrics for indels are the highest. Indel calling is more complicated than SNP calling, so this result is remarkable.

<p align="center">
  <img src="https://github.com/genomicsITER/benchmarking/blob/master/WGS/images/ConsistencyChallenge_results.png" width="45%">
  <img src="https://github.com/genomicsITER/benchmarking/blob/master/WGS/images/TruthChallenge_results.png" width="47.5%">
</p>

For Truth Challenge V2 we obtained good results for both SNPs and indels when comparing all benchmarked regions. But, when we focus on difficult-to-map regions metrics are lower, especially recall metrics. Lastly, MHC metrics were the worst, showing the high difficulty of variant calling in this region.

<p align="center">
  <img src="https://github.com/genomicsITER/benchmarking/blob/master/WGS/images/TruthChallenge-V2_results.png" width="70%">
</p>

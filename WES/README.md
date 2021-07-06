# Whole exome sequencing 

For whole exome sequencing benchmarking we created our own dataset by sequencing HG001 sample in our laboratory. In short, Nextera DNA Exome library preparation kit (Illumina) was used to prepare libraries from DNA samples. Then, samples were sequenced with paired-end 75bp at >50X on a HiSeq 4000 (Illumina). Once the reads are demultiplexed, we ran our variant calling pipeline. As in WGS benchmarking, we perform reads alignment with BWA-MEM and finally, variants were called using the HaplotypeCaller from the Genome Analysis Toolkit (GATK). A complete workflow is shown below.

<p align="center">
  <img src="https://github.com/genomicsITER/benchmarking/blob/master/WES/images/WES_workflow.png">
</p>

Furthermore, we obtained a WES reference dataset from WGS reference dataset by extracting the exonic regions capture with library preparation kit used to perform our WES comparison.

## Results

Our WES metric values were lower than those observed for WGS data. We think that this result might be related to the non-uniform coverage found in whole-exome sequencing enrichment when comparing to the data obtained from the Genome in a Bottle pilot sample for the same exonic regions.

<p align="center">
  <img src="https://github.com/genomicsITER/benchmarking/blob/master/WES/images/WES_results.png" width="40%">
</p>

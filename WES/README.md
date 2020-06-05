# Whole exome sequencing

Nextera DNA Exome (?) library preparation kit (Illumina) was used to prepare libraries from DNA samples. Then, samples were sequenced with paired-end 75bp at >50X on a HiSeq 4000 (Illumina) in our laboratory. Once the reads are demultiplexed, we ran our variant calling pipeline. First, we perform reads alignment with BWA-MEM and finally, variants are called using the HaplotypeCaller from the Genome Analysis Toolkit (GATK).

<p align="center">
  <img src="https://github.com/genomicsITER/benchmarking/blob/master/WES/images/WES_workflow.png">
</p>

## Results

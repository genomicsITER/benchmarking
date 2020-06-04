# Whole exome sequencing

Nextera DNA Exome (?) library preparation kit (Illumina) was used to prepare libraries from HG001 DNA sample. Then, the sample was sequenced with paired-end 75bp at >50X obtained on a HiSeq 4000 (Illumina) in our laboratory. Once the reads are demultiplexed, we ran our variant calling pipeline. First, we perform reads alignment with BWA-MEM and finally, variants are called using the HaplotypeCaller from the Genome Analysis Toolkit (GATK).

## Results

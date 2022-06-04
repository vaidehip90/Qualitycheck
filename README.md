# Qualitycheck
# Data from SRA
prefetch SRR6956031
fastq-dump -F--split-files--gzip SRR6956031

# quality check of data fastq.gz files
fastqc SRR6956031_1.fastq.gz
fastqc SRR6956031_2.fastq.gz

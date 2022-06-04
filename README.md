# Qualitycheck

# Data from SRA
prefetch SRR6956031

fastq-dump -F--split-files--gzip SRR6956031

# Quality check of data fastq.gz files
fastqc SRR6956031_1.fastq.gz

fastqc SRR6956031_2.fastq.gz

# Trimmomatic 
trimmomatic SE -phred33 SRR6956031_1.fastq.gz SRR6956031_1.trim.fastq.gz LEADING:3 TRAILING:3 SLIDINGWINDOW:4:20 MINLEN:100

trimmomatic SE -phred33 SRR6956031_2.fastq.gz SRR6956031_2.trim.fastq.gz LEADING:3 TRAILING:3 SLIDINGWINDOW:4:20 MINLEN:100

# Quality Check of Trimmed files
fastqc SRR6956031_1.trim.fastq.gz

fastqc SRR6956031_2.trim.fastq.gz



# ths-st1-tb

## Folders
1. `bam`, `results`, and `vcf`

These folders are created after running tb-profiler
- results
    - Contains **summary and profiling reports** for each sample.
    - Usually stores files in **JSON** and **text** (or it could be **CSV**) format that summarize:
        - Predicted drug resistance mutations
        - Strain lineage typing
        - Quality metrics
        - Other variant annotations and interpreted results
- bam
    - binary alignments of the input sequencing reads mapped to the reference genome (H37Rv)
- vcf
    - record the detailed list of DNA variants (SNPs, indels, etc.) identified by TBProfiler relative to the *Mycobacterium tuberculosis* reference genome

2. `fastq`

Folders that contain all the isolates downloaded from ENA. The files were downloaded in paired reads (i.e., it ends in `_1.fastq.gz` and `_2.fastq.gz`). The file name format is

`country_{ena_run}_{ena_accession}_{N}.fastq.gz`

- country - represents the country of the isolate
- ena_run - is the ena_run indicated in the excel sheet
- ena_accession - is the ena_run accession number when obtained from the ENA website using the API
- N - represents if it's a forward or reverse read

3. `tmp`

Temporary folder where all files that I don't know how and why it generated are placed.

4. `symlinks`

Since running tb-profiler requires following a certain format, the files follows the format: `{ena_accession}_{N}.fastq.gz`

5. `snp_only`

It contains all the VCF files that only contain the SNPs

6. `logs`

So the output in the notebook won't be messy, I placed all the output of tb-profiler here.

## Notebooks
1. `test.ipynb`

For testing lang, feel free to disregard. This is sort of like my scratch paper.

2. `download.ipynb`

Code to download all the files from the ENA API. 
As of July 18, I left a comment to change something for the next iteration of download.

3. `extract_snp.ipynb`

Code where you can run tb-profiler and extract the SNPs at the same time. The obtained SNPs are stored in the `snp_only` folder.

4. `process_snp.ipynb`

This is where the SNP matrix is saved. It follows the pre-processing of the Uganda study.

## Tools + Versions

TBProfiler
Trimmomatic
SnpEff?
SAMtools
bcftools

TBF hehe
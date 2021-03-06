# PLEASE data analysis by Eric Z Chen

## Data

#### Raw fastq files
All the fastq files are saved in the folder `1_COMBO_PLEASE` on the server. This folder contains three sub-folders:  
- `1_Raw_Fastq`: the raw fastq files.  
- `2_Quality_Filter`: the fastq files after removing the low quality reads.   
- `3_Remove_Human_DNA`: the fastq files after removing the low quality reads and human reads.  


#### Clinical data and sample information
- The raw clinical data are in the folder `1_Data/Raw_Data/Clinical_Information/`.
- The processed clinical data and sample information are in the folder `1_Data/Processed_Data/Sample_Information/`.


#### Bacterial abundance by MetaPhlAn
The MetaPhlAn outputs for COMBO samples and PLEASE samples are in the following folders. The "unclassfied" taxa were removed and the total relative abundance in each sample were normalized to be one.  "P","F","G","S" at the beginning of each file indicate taxonomic levels "phylum", "family", "genus", "species".  
- `1_Data/Raw_Data/MetaPhlAn/COMBO`  
- `1_Data/Raw_Data/MetaPhlAn/PLEASE`

## Analysis

#### Fastq data processing
- The raw fastq data were processed by FASTX to remove low quality reads. 
- Then the processed reads were aligned to human genome to remove human reads by Deconseq. The code is in `1_COMBO_PLEASE/Code_for_Human_Reads_Removal`.

#### Bacterial abundance quantification by MetaPhlAn
- The processed reads were used as input for MetaPhlAn. Since MetaPhlAn can only take single end reads as input and our data are pair-end reads, the paired reads (R1 and R2) were provided as two single end reads to MetaPhlAn. I also tested MetaPhlAn on the first read pair (R1) only and the results are quite similar to the previous ones. 





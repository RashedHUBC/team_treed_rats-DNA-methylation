# Results

## Milestone 1 - Data Preprocessing

### Sanity Checking DNA Methylation (Tony)
[1-Methylation_sanity_check.md](https://github.com/STAT540-UBC/team_treed_rats-DNA-methylation/blob/master/Data_Analysis/1-Methylation_sanity_check.md)
* Motivation
  * Performed sanity checks on DNA methylation data to check if anything funny is happening
* Results
  * Discovered that libraries have low coverage, so decided to pool replicates together
  * Noticed that female libraries have less coverage overall, which may influence results
  * Good that Estradiol and Male samples cluster together

  
### Data File Preparation for RNA-Seq data (Rashed)
[R codes for preparing files](https://github.com/STAT540-UBC/team_treed_rats-DNA-methylation/tree/master/Data_Analysis/RCode_RNAseq)
* Data Merginig
  * Merge all raw data files obtained after alignment with SAILFISH (done by Tony) in two ways for sanity check and differential expression analysis  
  * [Find the merged files with raw files](https://github.com/STAT540-UBC/team_treed_rats-DNA-methylation/tree/master/RNASeq_data/new_data_Tony_TPM)

### Sanity Checking RNAseq Data (Emma and David) 
[1-RNA_Seq_Sanity_Check.md](https://github.com/STAT540-UBC/team_treed_rats-DNA-methylation/blob/master/Data_Analysis/1-RNA_Seq_Sanity_Check.md)
* Motivation 
 * Same as with methylation data, the RNAseq data must be checked for any obvious anomalies or problems.
* Results 
 * A lot of genes were found to have an RPKM value of 0.
 * Replications in each group were highly correlated with one another. There is one particular sample that looks to be less correlated, although when actually looking at the values 0.97 correlation is good. Based on this, the gene was decided to be kept in. 


 
### Differential Expression Analysis (Male vs Female) (Tony and Rashed) 
[2-RNAseq_differential_expression.md](https://github.com/STAT540-UBC/team_treed_rats-DNA-methylation/blob/master/Data_Analysis/2-RNAseq_differential_expression.md)
* Motivation
  * The RNAseq data (raw counts) is used here for finding differentially expressed (DE) genes among male and female
* Different methods applied 
  *`edgeR` (`R` package) with usual negative binomial fitting and quasi-likelihood negative binomial fitting
  * Nonparametric method `NOISeq` (another `R` package)
  * Other conventional methods like `R` package `DESeq` and `limma` are also applied
* Result
  * We have found 164 DE genes among male vs female using `edgeR` with `glmQLFit`
  * 45 DE genes using `NOISeq`, 15 DE genes using `limma`
  * and 52 DE genes using `edgeR` with `glmFit`

### Differential Expression Analysis (Female vs FemaleZeb) (Tony) 
[3.1-DE_genes_femaleVSzeb.md](https://github.com/STAT540-UBC/team_treed_rats-DNA-methylation/blob/master/Data_Analysis/3.1-DE_genes_femaleVSzeb.md)

* Results
  * 43 genes were found to be differentially expressed between females and zeb-treated females following the same masculinizing gene expression pattern using `edgeR` with `glmQLFit`
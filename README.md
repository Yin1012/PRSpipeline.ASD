# `PRSpipline.ASD`



###### [Yin Yin](https://orcid.org/0000-0001-9168-488X), University of Toronto, Canada. &lt;yin.yin@mail.utoronto.ca&gt;
## 1 About this package:
This package describes the workflow to utilize GWAS data from MSSNG to build polygenic risk scores (PRS) for the prediction of autism spectrum disorder (ASD) risk. In this project, we also selected the best way to build PRS. Previous studies have limited ability to support sufficient risk prediction for polygenic inheritance of ASD because of the small size of GWASes and paucity of computational methods. Since Schizophrenia and education attainment are highly corelated with ASD as previously described, we can derive PRS by using GWAS of Schizophrenia and education attainment. 
## 2. Pipeline
### 2.1 GWAS statistics Download
 In our package, there were three main statistics needed: ASD, schizophrenia and EA. For ASD, the study we used is [Common risk variants identified in autism spectrum disorder](http://dx.doi.org/10.1101/224774). For schizophrenia , the study we used is [Biological insights from 108 schizophrenia-associated genetic loci. Nature. 2014](https://www.nature.com/articles/nature13595). For education attainment, the study we used is (Gene discovery and polygenic prediction from a genome-wide association study of educational attainment in 1.1 million individuals)[(https://www.nature.com/articles/s41588-018-0147-3). We downloaded the GWAS statistics of ASD and schizophrenia from [PGC](https://www.med.unc.edu/pgc/results-and-downloads) and downloaded the education attainment from [SSGAC](https://www.thessgac.org/data).
#### 2.1.1 Download GWAS statistics of ASD ad SCZ
1. go to [PGC](https://www.med.unc.edu/pgc/results-and-downloads)
2. Click *Download ASD GWAS - 2015* and *Download full SNP results* seperatly.
3. Finish data download agreement
4. You are good to download data

##### Brief view of ASD GWAS statistics
![alt text](https://github.com/Yin1012/PRSpipeline.ASD/blob/master/asd.PNG)

##### Brief view of SCZ GWAS statistics
![alt text](https://github.com/Yin1012/PRSpipeline.ASD/blob/master/scz.PNG)
#### 2.1.2 Download GWAS statistics of EA
```text
wget http://ssgac.org/documents/GWAS_EA.to10K.txt
```
##### Brief view of EA GWAS statistics
![alt text](https://github.com/Yin1012/PRSpipeline.ASD/blob/master/ea.PNG)
### 2.2 Download programs for building PRS 
In this project, we used two software pakcage for building PRS. First one is [PRSice](http://prsice.info/) which is a software package for calculating, applying, evaluating and plotting the results of polygenic risk scores. The second one is (ldpred)[https://github.com/bvilhjal/ldpred] which can be downloaded from github.
### 2.3 Building PRS and statistical analysis
ASDpipline_script in this package include:
1. Combine GWASs and making up missing columns
2. Run PRSice and LDpred to build 55 PRS by using different GWAS combinations, different parameters and different software.
3. Run PCA analyis and create related plots
4. Create stastistic table for final results (p-value and AUC)
## Acknowlegement.
I am very thankful Dr. Robert William Davis. This project is supported by he Hospital for Sick Children (SickKids).


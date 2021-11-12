# neuroCNVscore
The neuroCNVscore was developed to quantitatively prioritize the deleterious, functional and pathogenic CNVs in neurodevelopmental diseases on a genome wide basis. The core algorithm of neuroCNVscore is XGBoost. NeuroCNVscore outperformed in independent datasets and a well-known software SVScore. If you find neuroCNVscore useful in your work, please consider citing the neuroCNVscore paper (coming soon)

# Quick start
Before running the neuroCNVscore, make sure you have CNV data and feature matrix available. 

## CNV data
Input file format (a tab-delimited file): <br><br>

chr1    779525  1198561 loss <br>

Column 1: The chromosome  <br>
Column 2: Start <br>
Column 3: End <br>
Column 4: CNV type (gain or loss) <br>

## Feature matrix
### Feature source 
To run the neuroCNVscore on specific CNVs, these CNVs must be annotated with features.
A completed feature list could be found from feature folder or in supplemnetary table from our paper.

### Feature matrix generation
To run the shell script,please make sure you have bedtools (v2.29.2) installed. 
>Region
```Bash
bedtools intersect -a SVFILE -b FEATRUE -c
```
>RegionType
```Bash
 bedtools intersect -a SVFILE -b FEATRUE -f 0.5 -r -c
```
>RegionScore
```Bash
bedtools map -a  SVFILE -b FEATRUE -c 4 -o mean -null -9
```

## Main script
This script cnv_path_xgboost_202111.ipynb includes the main steps on input preprocessing, model training, prediction and performan evaluation.  Python version is 3.9.7 

## Pretained models
The trained models are currently provided in two types: copy number loss and copy number gain. 

# Hardware requirements
Our work was done at the linux x86_64 server with 144 CPUs, 1T memory. 



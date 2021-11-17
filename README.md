# neuroCNVscore
The neuroCNVscore was developed to quantitatively prioritize the deleterious, functional and pathogenic CNVs in neurodevelopmental diseases on a genome wide basis. The core algorithm of neuroCNVscore is XGBoost. NeuroCNVscore outperformed a state-of-art tool in independent datasets. If you find neuroCNVscore useful in your work, please consider citing the neuroCNVscore paper (coming soon)

# Quick start
You need both CNV data and feature matrix to run the neuroCNVscore. 

## CNV data
Input file format (a tab-delimited file): <br><br>
Example: chr1    779525  1198561 loss <br>
Column 1: The chromosome  <br>
Column 2: Start <br>
Column 3: End <br>
Column 4: CNV type (gain or loss) <br>

## Feature matrix
### Feature source 
CNVs must be annotated with neuro specific features. A completed feature list could be found under feature folder or at supplemnetary table from our paper. 

### Feature matrix generation
To run the script,please make sure you have bedtools (v2.29.2) installed. And all the FEATRUE files shall be in bed format including: chromosome, start, end and score/information.

>Region
```Bash
bedtools intersect -a CNVFILE -b FEATRUE -c
```
>RegionType
```Bash
 bedtools intersect -a CNVFILE -b FEATRUE  -f 0.5 -F 0.5 -e -c
```
>RegionScore
```Bash
bedtools map -a  SVFILE -b CNVFILE -c 4 -o mean -null 0
```
An example of output is provided as: copy_number_loss_example.bed

## Pretained models
The trained models are currently provided in two types: copy number loss and copy number gain. 

## Main script
This script cnv_path_xgboost_202111.ipynb includes the main steps on input preprocessing, model training, prediction and performan evaluation.  Python version is 3.9.7 

### Prediction interpretation
Generally, higher predicted score is more likely to be pathogenic, and lower predicted score is considering to be benign. Empirically, a score is higher than 0.68 is considered as pathogenic.

# Hardware requirements
Our work was done at the linux x86_64 server with 144 CPUs, 1T memory. 



# neuroCNVscore
The neuroCNVscore was developed to quantitatively prioritize the deleterious, functional and pathogenic CNVs in neurodevelopmental diseases on a genome wide basis. The core algorithm of neuroCNVscore is XGBoost. NeuroCNVscore outperformed in independent datasets and a well-known software SVScore. If you find neuroCNVscore useful in your work, please consider citing the neuroCNVscore paper (coming soon)

# Quick start
## Feature source 
To run the neuroCNVscore on specific CNVs, these CNVs must be annotated with features.
A completed feature list could be found from feature folder or in supplemnetary table from our paper.

## Feature matrix generation
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

## Pretained models
The trained models are currently provided in two types: copy number loss and copy number gain. 





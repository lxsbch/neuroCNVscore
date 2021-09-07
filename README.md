# neuroCNVscore
The neuroCNVscore was developed to quantitatively prioritize the deleterious, functional and pathogenic CNVs in neurodevelopmental diseases on a genome wide basis. The core algorithm of neuroCNVscore is XGBoost. NeuroCNVscore outperformed in independent datasets and a well-known software SVScore. If you find neuroCNVscore useful in your work, please consider citing the neuroCNVscore paper (coming soon)

# Quick start
## Feature matrix generation

To run the predictor on specific CNVs, these CNVs must be annotated with features.

feature_process.sh is the main script to process features from gene, functional and sequence levels. 

* Usage: sh feature_process.sh [Master File] [Feature File]
Master file is the interested CNVs in bed format.

Feature file includes the pathes of all preprocessed features in bed format 


## Pretained models
The trained models are currently provided in two types, copy number loss and copy number gain. 





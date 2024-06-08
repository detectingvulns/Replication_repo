Instructions for replicating and using our study related artifacts.

The Folder "DeeptraVul" contains the training scripts and the model weights for the DeeptraVul model. 
The Folder "SCRIPTS" contains the Data Collection and the Experiment related artifacts.


To replicate our study:
* Use the PCVES.csv and NVD_DF.csv which provides the list of PCVE IDs and their corresponding NVD public disclosure date. Use these files as a starting point for identifying CVES for which you want to collect data, perform experiments, replicate the study. etc
* Start with the instructions outlined in ./SCRIPTS/DATA_COLLECTION/readme.txt and collect the necessary data. 
* To replicate the experiments follow the instructions outlined in in the ./SCRIPTS/EXPERIMENTS/SOTA_EXPERIMENTS/readme.txt
* To use our model, you can navigate to the ./DeeptraVul/EVALUATION/model and get the model weights.
* To use our dataset, you can navigate to the ./DeeptraVul/EVALUATION/eval_dataset/eval_dataset.csv and ../DeeptraVul/TRAINING/delice_training_dataset.csv

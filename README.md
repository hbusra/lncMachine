# lncMachine
lncMachine (2021): Machine learning–based pipeline for genome-wide lncRNA discovery and annotation

## Key Highlights
- ML–based pipeline for genome-wide lncRNA discovery and annotation
- Supports supervised model training and prediction using multiple classifiers
- Published and benchmarked in [Functional & Integrative Genomics (2021)](https://link.springer.com/article/10.1007/s10142-021-00769-w?_lrsc=46a0ab3f-f584-4075-9711-b582de4af086)
- Designed for reproducible, large-scale transcriptomic annotation workflows

## Overview
lncMachine is designed for genome-wide identification and annotation of lncRNAs using supervised machine learning. It supports model training from user-provided coding and noncoding datasets as well as prediction using prebuilt models.

Prediction models were constructed using the sklearn module (version 0.22). Prebuilt models are provided and should be used with the same sklearn version for compatibility.

## Requirements
- Python 3 or newer
- scikit-learn version 0.22

**Required Python packages:**
- Bio
- optparse
- numpy
- pandas
- sklearn
- pickle


## Program Usage

```
Options:
--version             show program's version number and exit  
-h, --help            show this help message and exit
-c CODING_FILE, --cod=CODING_FILE
		      Coding sequences in fasta format
-n NONCODING_FILE, --noncod=NONCODING_FILE
		      Noncoding sequences in fasta format. Required for
			  training.
--train               Train using coding and noncoding datasets
		      [default:RandomForestClassifier(random_state=1,
		      n_jobs=-1)]. Both -n and -c required.
--all                 Build models for all nine algorithms.
--model=PREDICTION_MODEL
		      Prediction model in .sav format [optional]
--algorithm=ALGORITHM
		      Use specified machine learning prediction algorithm
		      i.e. RandomForestClassifier(random_state=1, n_jobs=-1)
-i ICSV               Tab separated CSV file containing class and feature
		      information [optional]
-o OUTPUT_FILE, --out=OUTPUT_FILE
		      Output file name for classification (1 for coding and
		      0 for noncoding) and the features
		      [default:'features.csv'].
```

## Example Workflows

**Build a Random Forest prediction model from coding and noncoding FASTA files:**
```
python3 lncMachine.py -c coding.fasta -n noncoding.fasta --train 
```

**Build prediction models using nine ML algorithms:**
```
python3 lncMachine.py -c coding.fasta -n noncoding.fasta --train --all
```

**Train a Random Forest model from a CSV file containing at least two classes:**
```
python3 lncMachine.py -i features.csv --train
```

**Predict coding probability from a FASTA file using a prebuilt model:**
```
python3 lncMachine.py -c coding.fasta --model prebuilt_model.sav
```

## Citation
Cagirici et al.,
“lncMachine: a machine learning-based approach for genome-wide identification of long noncoding RNAs”
Functional & Integrative Genomics, 2021

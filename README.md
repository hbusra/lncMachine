# lncMachine (2021): Machine learning tool for genome-wide lncRNA discovery and annotation
[![DOI](https://img.shields.io/badge/DOI-10.1007%2Fs10142--021--00769--w-blue)](https://doi.org/10.1007/s10142-021-00769-w)
![Python](https://img.shields.io/badge/Python-3+-yellow)

> **📄 Publication:** lncMAchine: A machine learning-based approach for genome-wide identification of long noncoding RNAs — [Functional & Integrative Genomics, 2021](https://doi.org/10.1007/s10142-021-00769-w)<br/>
> **👤 Role:** First author and primary developer — implemented ML pipeline and prediction framework<br/>
> **🎯 Impact:** Enables supervised genome-wide lncRNA discovery and annotation with multiple classifiers<br/>
> **Tech:** Python 3 • scikit-learn • BioPython • NumPy • pandas


## Overview
lncMachine is designed for genome-wide identification and annotation of lncRNAs using supervised machine learning. Users can train models from coding and noncoding sequences and apply prebuilt models for prediction. lncMachine supports multiple classifiers and ensures reproducibility with reference code matching the publication.

**Use cases:** lncRNA annotation in new genomes • Comparative genomics • Model evaluation and classifier benchmarking


## Requirements
- Python 3 or newer
- scikit-learn version 0.22
- BioPython
- Numpy
- pandas


## Installation
Clone the repository and ensure dependencies are installed:
```
git clone https://github.com/hbusra/lncMAchine.git
cd lncMAchine
pip install -r requirements.txt
```

**Note:** Prebuilt models require scikit-learn 0.22 for compatibility.


## Example Usage

**Train a Random Forest prediction model from coding and noncoding FASTA files:**
```
python3 lncMachine.py -c coding.fasta -n noncoding.fasta --train 
```

**Train prediction models with nine ML algorithms:**
```
python3 lncMachine.py -c coding.fasta -n noncoding.fasta --train --all
```

**Train from a CSV feature file:**
```
python3 lncMachine.py -i features.csv --train
```

**Predict coding probability from a FASTA file using a prebuilt model:**
```
python3 lncMachine.py -c test.fasta --model prebuilt_model.sav -o test_predictions.csv
```

## Citation
Cagirici et al.,
“lncMachine: a machine learning-based approach for genome-wide identification of long noncoding RNAs”
Functional & Integrative Genomics, 2021

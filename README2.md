# ThpPred
A method for predicting therapeutic and non-therapeutic proteins

# Introduction
ThpPred is developed for predicting, designing and scanning therapeutic peptides. More information on ThpPred is available from its web server http://webs.iiitd.edu.in/raghava/thppred. This page provide information about standalone version of ThpPred.

# Standalone

Standalone version of ThpPred is written in python and the following libraries are necessary for a successful run:

- scikit-learn
- Pandas
- Numpy
- Bio
- XGBoost
- Onnxruntime


**Minimum USAGE** 

To run the example, type the following command:
```
python thppred_stand.py

```

**Full Usage**: 

To run the code with your parameters, type the following command:
```
python thppred_stand.py |Input_File| |Model| |Threshold|

```
Example Command:
```
python thppred_stand.py file.fasta 1 0.5

```

**Input File**: It allow users to provide input in FASTA format. User should provide the file name along with its full path in case the input file is not in the same folder as the thppred_stand.py file.

**Model**: In this program, four models have been incorporated;  
  i) Model1 for predicting given input peptide/protein sequence as therapeutic and non-therapeutic peptide/proteins using XGBoost based on amino-acid composition of the peptide/proteins; 

  ii) Model2 for predicting given input peptide/protein sequence as therapeutic and non-therapeutic peptide/proteins using Hybrid approach, which is the ensemble of XGBoost + Motif Score. It combines the scores generated from machine learning (XGB), and motif occurence as Hybrid Score, and the prediction is based on Hybrid Score.
	
  iii) Model3 for predicting given input peptide/protein sequence as therapeutic and non-therapeutic peptide/proteins using random forest based on dipeptide composition of the peptide/proteins; 

  iv) Model4 for predicting given input peptide/protein sequence as therapeutic and non-therapeutic peptide/proteins using Hybrid approach, which is the ensemble of Random forest + Motif Score. It combines the scores generated from machine learning (RF), and motif occurence as Hybrid Score, and the prediction is based on Hybrid Score.
  
  User must enter model number(1,2,3 or 4) in the command line, else default value will be considered i.e. 2.


**Threshold**: User should provide a threshold value that lies between 0 and 1, please note score is proportional to therapeutic potential of peptide.
 
	User must enter a valid threshold value in the command line, else default value will be considered i.e. 0.5.




ThpPred Package Files
=======================
It contain following files, brief description of these files given below

INSTALLATION  	: Installation instructions

LICENSE       	: License information

README.md     	: This file provide information about this package

thppred_stand.py 	: Main python program 

rf_model.onnx       : Model file required for running RF based Machine-learning model

xgb_model.onnx      : Model file required for running XGB based Machine-learning model

example.fasta	: Example file contain protein/peptide sequences in FASTA format. User may use this for test run.

# Reference

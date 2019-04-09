# CS-590U---Final-Project

The goal of our project is to give a breakdown of a 2-person conversation. To facilitate our work, we are using [pyAudioAnalysis](https://github.com/tyiannak/pyAudioAnalysis), a Python library for audio feature extraction, classification, segmentation and applications.

There are two main stages to our model: Speaker Diarization and Classifcation.

# Speaker Diarization

Given an audio file containing a conversation between two people, we would like a way to distinguish who is speaking at a given point in time. Speaker diarization does just that, informing us who is speaking.

# Classification

Once we have a means of partitioning a conversation into Speaker 1 and Speaker 2, we would like to classify their audio into three categories: talking, laughing, and filler words ('Uhh', 'Eh', "Um'). 

## Step 1
### Read in Wave Files. 

## Step 2 
### Convert Stereo to Mono - Wave Files have two channels; we want to handle one of them.

## Step 3 
### Obtain Short-Term Features using a window size of 0.05 and a step size of 0.05. There are 34 of such features:

* Zero Crossing Rate
* Energy
* Entropy of Energy
* Spectral Centroid
* Spectral Spread
* Spectral Entropy
* Spectral Flux Mean
* Spectral Rolloff
* 13 different Mel Frequency Cepstral Coefficients
* 12 different Chroma Vectors 
* Chroma Standard Deviation

## Step 4
### Obtain Mid-Term Features using a window size of 1 and a step size of 1. There are 68 of such features which extracts the mean and standard deviation of all of the short-term features. 

34 short-term features * (Mean and Standard Deviation) = 68 mid-term features

## Step 5
### Collapse the 68 different features down to a single feature vector by taking the mean of each vector. This results in a 64 X 1 vector for an entire audio file.

## Step 6
### Normalize the data by centering the data with a mean of 0 and seting the standard deviation to 1. This is just standard practice in machine learning.

## Step 7
### Repeat steps 1-6 for every single audio file, each file belonging to a particular class. This results in a bunch of "64 X 1" vectors, each representing one file. 

## Step 8 
### Run classifcation algorithms and tune their hyperparameters. Obtain their Precision/Recall/F1-Score as metrics to evaluate these models. 



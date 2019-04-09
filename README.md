# CS-590U---Final-Project

The goal of our project is to give a breakdown of a 2-person conversation. To facilitate our work, we are using [pyAudioAnalysis](https://github.com/tyiannak/pyAudioAnalysis), a Python library for audio feature extraction, classification, segmentation and applications.

There are two main stages to our model: Speaker Diarization and Classifcation.

# Step 1: Speaker Diarization

Given an audio file containing a conversation between two people, we would like a way to distinguish who is speaking at a given point in time. Speaker diarization does just that, informing us who is speaking.

# Step 2: Classification

Once we have a means of partitioning a conversation into Speaker 1 and Speaker 2, we would like to classify their audio into three categories: talking, laughing, and filler words ('Uhh', 'Eh', "Um'). 



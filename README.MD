# Spoken Language Analysis

### Background

This case study is done as part of a job application process and as well as a practice exercise for audio data analysis. The data was taken from Kaggle https://www.kaggle.com/toponowicz/spoken-language-identification .

### Objective

To create a classification model for the spoken languages which includes English, German and Spanish.

### Dataset

The dataset is divided into 2 directories:
* train (73080 samples)
* test (540 samples)

Each sample is an FLAC audio file with:
* sample rate: 22050
* bit depth: 16
* channels: 1
* duration: 10 seconds (sharp)

Total size of the data is about 15GB.

### Processes

1. Download the .zip file from the Kaggle page above.
2. Unzip both the <train> and <test> folders into ```<work_directory>/data/```.
3. Install the latest Anaconda
4. Install required libraries listed in the IPython notebook.
5. Run Jupyter Notebook
6. Run the ```Spoken Language.ipynb``` notebook
    
The extracted features and labels are included in the file <language_feat.npy> and <language_label.npy> and can be loaded directly instead of running the feature extraction function again.
    
### Approach

As I don't have any prior experience in audio data analysis, I refer to https://github.com/micah5/pyAudioClassification as guidance for a simple classification model.

There is not much data cleaning or manipulation that has been done as I'm still exploring the data structure of audio data.

The code references are using ```keras, librosa, tensorflow``` and other libraries listed in the IPython notebook for its model.

Since the training data is too big to process with the limited resources that I have, thus I sampled the data to 10x the test data (540 x 10 = 5400 samples), so I only take the first 1800 data from each languages.

### Results

The code work well until the feature extraction step, but returned error during the model training step. Since, I referenced from a ready-made code, I assumed there might be a need to modify the code to adapt to my data. Therefore, a further detailed inspection of the functions is required.

### Future Goal

Explore more about data structure of an audio data files and learn how to clean and prepare it to be used for model training.

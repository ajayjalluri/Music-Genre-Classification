# Pre Trained VGG16 for Genre classification
Trained CNN model for Genre classification on GTZAN dataset 
## Overview
For train CNN model of deep learning:

1. Read the audios as melspectrograms, spliting them into 3s windows with 50% overlaping resulting in a dataset with the size 19000x129x128x1 (samples x time x frequency x channels)**.
2. Shuffle the input and split into train and test (70%/30%)
3. Train the CNN and validate using the validation dataset

** In the case of the VGG, the channel need to have 3 channels
## GTZAN -- Datasets   

The dataset consists of 1000 audio tracks each 30 seconds long. It contains 10 genres, each represented by 100 tracks. The tracks are all 22050Hz Mono 16-bit audio files in .wav format.    
Classes: blues, classical, country, disco, hiphop, jazz, metal, pop, reggae, rock
## Data preprocessing
Before training the classification model, we have to tranform raw data from audio samples into more meaningful representations. [Librosa](https://github.com/librosa/librosa) has several methods for extracting various useful audio features: STFT (Short-Time Fourier Transform), Mel-spectrogram, MFCC (Mel-frequency cepstral coefficients), CQT (Constant-Q Transform), Harmonic-Percussive spectrogram, Chromagram .<br>
Having a big data set isn't enough, in oppose to image tasks I cannot work straight on the raw sound sample, a quick calculation: 30 seconds × 22050 sample/sec- ond = 661500 length of vector, which would be heavy load for a convention machine learning method.
Following all the papers I read and researching a little on acoustic analysis, It is quit obvious that the industry is using Mel-spectrogram as the feature vector for the sound sample, I used librosa implementation.
<p align="center">
<img src= https://github.com/ajayjalluri/Music-Genre-Classification/blob/master/imgs/1.PNG?raw=true>
</p>

## Transfer Learning
I used the pretrained model of VGG16 as feature extractors using Google Colab GPU. 
## Model Summary
<p align="center">
<img src= https://github.com/ajayjalluri/Music-Genre-Classification/blob/master/imgs/Model%20Summary.PNG?raw=true>
</p>
## HElPFULL RESOURCES
**https://towardsdatascience.com/step-by-step-guide-to-using-pretrained-models-in-keras-c9097b647b29
**https://towardsdatascience.com/transfer-learning-from-pre-trained-models-f2393f124751





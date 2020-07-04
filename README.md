# Pre Trained VGG16 for Genre classification
Trained CNN model for Genre classification on GTZAN dataset 
## Overview
For train CNN model of deep learning:

1. Read the audios as melspectrograms, spliting them into 3s windows with 50% overlaping resulting in a dataset with the size 19000x129x128x1 (samples x time x frequency x channels)**.
2. Shuffle the input and split into train and test (70%/30%)
3. Train the CNN and validate using the validation dataset

** In the case of the VGG, the channel need to have 3 channels
## Data preprocessing

Before training the classification model, we have to tranform raw data from audio samples into more meaningful representations. [Librosa](https://github.com/librosa/librosa) has several methods for extracting various useful audio features: STFT (Short-Time Fourier Transform), Mel-spectrogram, MFCC (Mel-frequency cepstral coefficients), CQT (Constant-Q Transform), Harmonic-Percussive spectrogram, Chromagram . 
## Representing Music as Image
A very naive idea of mine was to simply plot the y values as shown below. <br>
<img src="imgs/index.png"> <br>
By soon I realized that it won't just work as it doesn't give much information about tones and decided to go for melspectograms. <br>
A spectrogram is a visual representation of the spectrum of frequencies of sound or other signal as they vary with time. Spectograms allow looking at the whole song once and get the information about the tones present right away! <br>
<img src="imgs/pop.png" width=45% title="POP"><img src="imgs/classical.png" width=45% title="CLASSICAL"> <br>
These looked quite promising to me and so created a dataset using <a href='https://github.com/Insiyaa/Music-Genre-Classification/blob/master/create_dataset.ipynb'>this</a> notebook.

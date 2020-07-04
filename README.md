# Pre Trained VGG16 for Genre classification
Trained CNN model for Genre classification on GTZAN dataset 
## Overview
For train CNN model of deep learning:

1. Read the audios as melspectrograms, spliting then into 3s windows with 50% overlaping resulting in a dataset with the size 19000x129x128x1 (samples x time x frequency x channels)**.
2. Shuffle the input and split into train and test (70%/30%)
3. Train the CNN and validate using the validation dataset

** In the case of the VGG, the channel need to have 3 channels

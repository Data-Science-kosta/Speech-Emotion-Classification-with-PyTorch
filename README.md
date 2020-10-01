# Speech-Emotion-Classification-with-PyTorch
This repository contains PyTorch implementation of 4 different models for classification of emotions of the speech.
## DATASET
Models are trained on [RAVDESS Emotional Speech Audio](https://www.kaggle.com/uwrfkaggler/ravdess-emotional-speech-audio) dataset. It consits of 1440 speech audio-only files (16 bits, 48kHz, .wav).<br />
Dataset is balanced:<br />
![dataset1](https://github.com/Data-Science-kosta/Speech-Emotion-Classification-with-PyTorch/blob/master/garbage/1.png) <br />
Emotions have 2 intensities, **strong** and **normal** (except for the **neutral** emotion, which only has **normal** intensity): <br />
![dataset2](https://github.com/Data-Science-kosta/Speech-Emotion-Classification-with-PyTorch/blob/master/garbage/2.png) <br />
## PREPROCESSING
Data 

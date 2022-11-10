# Speech-Emotion-Classification-with-PyTorch
This repository contains PyTorch implementation of 4 different models for classification of emotions of the speech:
1. Stacked Time Distributed 2D CNN - LSTM
2. Stacked Time Distributed 2D CNN - Bidirectional LSTM with attention
3. Parallel 2D CNN - Bidirectional LSTM with attention
4. Parallel 2D CNN - Transformer Encoder
## DATASET
Models are trained on [RAVDESS Emotional Speech Audio](https://www.kaggle.com/uwrfkaggler/ravdess-emotional-speech-audio) dataset. It consits of 1440 speech audio-only files (16 bits, 48kHz, .wav).<br />
Dataset is balanced:<br />
![dataset1](https://github.com/Data-Science-kosta/Speech-Emotion-Classification-with-PyTorch/blob/master/garbage/1.png) <br />
Emotions have 2 intensities: **strong** and **normal** (except for the **neutral** emotion, which only has **normal** intensity). <br />
![dataset2](https://github.com/Data-Science-kosta/Speech-Emotion-Classification-with-PyTorch/blob/master/garbage/2.png) <br />
## PREPROCESSING
Signals are loaded with sample rate of 48kHz and cut off to be in the range of [0.5, 3] seconds. If the signal is shorter than 3s it is padded with zeros.<br />
**MEL spectrogram** is calculated and used as an input for the models (for the 1st and 2nd model the spectrogram is splitted into 7 chunks).<br />
Example of the MEL spectrogram:<br />
![spectrogram](https://github.com/Data-Science-kosta/Speech-Emotion-Classification-with-PyTorch/blob/master/garbage/4.png) <br />
Dataset is splitted into train, validation and test sets, with following percentage: (80,10,10)%.<br />
**Data augmentation** is performed by adding [Additive White Gaussian Noise](https://en.wikipedia.org/wiki/Additive_white_Gaussian_noise) (with SNR in range [15,30]) on the original signal. This enormously improved accuracy and removed overfitting.<br />
Datasets are scaled with **Standard Scaler**.<br />
## MODELS
Architectures for all 4 models are shown from left to right respectively:<br />
<br />
![spectrogram](https://github.com/Data-Science-kosta/Speech-Emotion-Classification-with-PyTorch/blob/master/garbage/100.png) <br />
## RESULTS 
**1. Model**: <br />
Accuracy: **94.02%**

Confusion Matrix             |  Influence of Emotion intensity on correctness
:-------------------------:|:-------------------------:
![KM1](https://github.com/Data-Science-kosta/Speech-Emotion-Classification-with-PyTorch/blob/master/garbage/KM%20model1.png)  |  ![EI1](https://github.com/Data-Science-kosta/Speech-Emotion-Classification-with-PyTorch/blob/master/garbage/EI%20model1.png)

**2. Model**: <br />
Accuracy: **96.55%**

Confusion Matrix             |  Influence of Emotion intensity on correctness
:-------------------------:|:-------------------------:
![KM2](https://github.com/Data-Science-kosta/Speech-Emotion-Classification-with-PyTorch/blob/master/garbage/KM%20model2.png)  |  ![EI2](https://github.com/Data-Science-kosta/Speech-Emotion-Classification-with-PyTorch/blob/master/garbage/EI%20model2.png)

**3. Model**: <br />
Accuracy: **95.40%**

Confusion Matrix             |  Influence of Emotion intensity on correctness
:-------------------------:|:-------------------------:
![KM3](https://github.com/Data-Science-kosta/Speech-Emotion-Classification-with-PyTorch/blob/master/garbage/KM%20model3.png)  |  ![EI3](https://github.com/Data-Science-kosta/Speech-Emotion-Classification-with-PyTorch/blob/master/garbage/EI%20model3.png)

**4. Model**: <br />
Accuracy: **96.78%**

Confusion Matrix             |  Influence of Emotion intensity on correctness
:-------------------------:|:-------------------------:
![KM4](https://github.com/Data-Science-kosta/Speech-Emotion-Classification-with-PyTorch/blob/master/garbage/KM%20model4.png)  |  ![EI4](https://github.com/Data-Science-kosta/Speech-Emotion-Classification-with-PyTorch/blob/master/garbage/EI%20model4.png)




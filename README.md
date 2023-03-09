# Digital-Signal-Image-Management

# Overview
The project consists in the development of an application for the recognition of one-dimensional signals (audio) and two-dimensional signals (images). Specifically we have developed three different task:

* Processing-1D: Recognize the class to which an urban sound belongs with ML and DL models. For solve this task we have tried different models and different configuration of features (energy, zero crossing rate, mfcc, spectrogram, etc...)
* Processing-2D: Correctly classify the state of health (healthy/unhealthy) and the crop species with DL models, so it's a multi label multi class classification. In this case we created CNN from scratch and we also tried different pretrained architecture with weights based on general task (ImageNet).
* Retrieval: Find the ten images most similar to the input image, using both a pretrained neural network and an autoencoder as feature extractor 

# Data
All the data used for this project were collected directly in the following ways:
* Processing-1D: UrbanSound8K dataset from https://urbansounddataset.weebly.com/urbansound8k.html
* Processing-2D: PlantVillage dataset from https://github.com/spMohanty/PlantVillage-Dataset. In this project we used a subset of the data consisting of 15,000 images and we grouped the different leaf diseases so that we could classify the leaf image as healthy or unhealthy.
* Retrieval: Food-101 dataset from https://www.kaggle.com/datasets/kmader/food41

# How to run code
Unless otherwise specified in the notebook section all codes can be runned in [Google Colaboratory](https://colab.research.google.com/) platform. All notebooks all already setted to import the necessary packages and also in this way you can easily use a GPU! <br>

# Results Table
Comparative result of models based on test set created by subsampling the original dataset:

* Processing-1D: 

SVM Classification

   | Features | Accuracy | 
   | ----- | ----------- | 
   | Energy | 0.20 | 
   | Duration| 0.18 | 
   | Zero Crossing Rate | 0.20 |
   | Spectrogram | 0.11 |
   | Mel Spectrogram | 0.26 |
   | MFCC | 0.17 |
   | Energy + Duration | 0.20 |
   | **Energy + Duration + Zero Crossing Rate** | 0.42 |
   
CNN on Mel Spectrogram
   
   | Architectures | Training Accuracy | Validation Accuracy | 
   | ----- | ----------- | ------------ | 
   | 3 convolutional layers <br>ReLu <br>Max Pooling <br>Dropout <br>1 dense layer | 0.98 | 0.89 | 
   | 3 convolutional layers <br>ReLu <br>Max Pooling <br>Batch Normalization <br>Dropout <br>1 dense layer | 0.96 | 0.86 | 
   
* Processing-2D:

The results obtained with the best CNN from scratch and with the pretrained architectures are shown

  | Architectures | Training Accuracy | Validation Accuracy | Training Loss | Validation Loss |
  | ----- | ----------- | ------------ | -------------- | --------------- |
  | **CNN from scratch** | 0.79 | 0.85 | 0.21 | 0.19 |
  | MobileNet-V2 | 0.53 | 0.57 | 0.50 | 0.49 |
  | ResNet-50 | 0.56 | 0.55 | 0.49 | 0.47 |


# About us

#### Aurora Cerabolini - Data Science Student @ University of Milano-Bicocca
  * [GitHub](https://github.com/AuroraCerabolini)
  * [LinkedIn](https://www.linkedin.com/in/aurora-cerabolini)

#### Veronica Morelli - Data Science Student @ University of Milano-Bicocca
  * [GitHub](https://github.com/veronicamorelli)
  * [LinkedIn](https://www.linkedin.com/in/veronica-morelli-a854bb224)

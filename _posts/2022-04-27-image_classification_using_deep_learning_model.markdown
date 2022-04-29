---
layout: post
title:      "Image Classification using deep learning model"
date:       2022-04-27 23:40:30 -0400
permalink:  image_classification_using_deep_learning_model
---


My major in university is Biomedical Engineering, in which medical image processing is a major field. I have previously learned image segmentation, image reconstruction, and image classification, etc. However, I have not used deep learning models in these analyses before, since deep learning model has not been proposed when I am a student in the collage. And I am glad to have a chance to do medical image classification using deep learning model.

In this project, I tried to do image classification of chest xray images to see whether it is belonging to a healthy person or a patient with pneumonia, with the images download from kraggle:  ![](https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia)

The images I am going to deal with in this project are shown like these:
![](https://raw.githubusercontent.com/eegshou/dsc_proj4/main/figures/xchestimage.png)

Well, I am not a radiologist, it is really hard for me to judge whether the xray image shows Pneumonia or not. Fortunately, we have machine learning, specifically, we have supervised machine learning to let the computer judge whether it is pneumonia or normal after learning from tens and thousands images.

The dataset I downloaded from kraggle has already been splitted into three folders, i.e., train, validation, and test. At first, I found there are only 8 images in the validation folder for both normal and pneumonia. Therefore, I moved 150 images from training folder to validation folder. And finally, the number of images in each folder is shown below:
![](https://raw.githubusercontent.com/eegshou/dsc_proj4/main/figures/numimagesfinal.png)

Then I used training and validation dataset for comparing eight different types of models:
- a baseline dense model (termed as model_dense)
- a CNN model (model_cnn)
- a CNN model with data augmentation (model_cnnda)
- a CNN model with batch Normalization (model_cnnbn)
- a CNN model with dropout (model_cnndo)
- a pretrained VGG19 model with the CNN model (model_cnnvgg0)
- a pretrained VGG19 model with a new CNN model (model_cnnvgg1)
- the model_cnnvgg0 with a new data augmentation (model_cnnvgg0da2)
- the model_cnnvgg0 with a new data augmentation (model_cnnvgg1da2)

And the final results for these different models on the test data are shown below:
![](https://raw.githubusercontent.com/eegshou/dsc_proj4/main/figures/modelcomp_testlossacc.png)

It seems that the cnnvgg models are slight better, while they are generally similar except the baseline dense model

Finally, I chose the model_cnnvgg1 as the model to generate the final results:
- Accuracy: 90.54%
- Precision: 88.22%
- Recall: 97.94%
- F1-score: 92.83
 ![](https://raw.githubusercontent.com/eegshou/dsc_proj4/main/figures/FinalModel_conf.png)

### Summary

- It achieves above 90% accuracy, with the use of VGG19 model
- With more adjustment and more data, the accuracy will be further improved









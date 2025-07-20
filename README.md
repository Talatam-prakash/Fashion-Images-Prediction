# Fashion Product Image Prediction
This project uses a deep learning model to automatically predict multiple attributes of a fashion product—such as gender, color, category, and season—directly from its image. 

## Project Overview
In the e-commerce fashion industry, manually tagging products with attributes is a slow, labor-intensive, and often inconsistent process. This project aims to solve that problem by providing an automated system that accurately analyzes a product image and assigns relevant tags.

The core of this project is a multi-output Convolutional Neural Network (CNN) that takes an image as input and simultaneously predicts seven different attributes.

## Key Features
- Multi-Output Prediction: The model predicts seven attributes in a single forward pass:

  1. Gender: Men, Women, Boys, Girls, Unisex

  2. Master Category: Apparel, Accessories, Footwear, etc.

  3. Sub Category: Topwear, Shoes, Bags, etc.

  4. Article Type: T-Shirts, Jeans, Watches, etc.

  5. Base Color: Blue, Red, Black, etc.

  6. Season: Summer, Winter, Fall, Spring

  7. Usage: Casual, Sports, Formal, etc.

- Deep Learning Model: Built with TensorFlow and Keras, using a CNN architecture optimized for image classification tasks.


## Dataset
The model was trained on the Fashion Product Images Dataset. This dataset contains thousands of images of fashion articles, each associated with detailed metadata including the attributes our model predicts.

- Source: https://www.kaggle.com/datasets/paramaggarwal/fashion-product-images-dataset

- Size: Contains over 44,000 images.

## Model Architecture
This project leverages transfer learning by using the pre-trained VGG16 model as its convolutional base. This approach allows us to benefit from the powerful feature extraction capabilities of a model trained on the massive ImageNet dataset.

1. Input Layer: Accepts images resized to (128, 128, 3).

2. Base Model (VGG16): The VGG16 model, with its weights pre-trained on ImageNet, is used as a fixed feature extractor. The convolutional layers of VGG16 are frozen to prevent them from being updated during training.

3. Custom Head: On top of the VGG16 base, a custom classification head is added:

  - A Flatten layer to convert the 2D feature maps from VGG16 into a 1D vector.

  - A Dense layer with ReLU activation for further feature processing.

  - A Dropout layer for regularization to prevent overfitting.

- Multi-Output Layers: Seven separate Dense output layers are connected to the custom head, one for each attribute (Gender, Color, etc.). Each output layer uses a softmax activation function to generate the final classification probabilities.

By using transfer learning, we significantly reduce training time and can achieve high accuracy even with a smaller dataset.

# Technology used
- Tensorflow
- Keras
- pandas
- numpy
- Pillow
- matplotlib
- seaborn
- scikit learn



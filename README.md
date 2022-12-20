# Crop-Disease-Detection
A deep learning project for plant disease detection using tensorflow

Given a dataset of images of healthy and diseased crops' leaves, this project classifies healthy crops and diseased crops.
Below is an example of a healthy leaf of a crop.

![Screenshot 2022-12-20 120546](https://user-images.githubusercontent.com/78556152/208627955-c203a0fb-e401-4eb7-99bc-32481611242a.png)

## Defining some parameters for the loader

Batch size is set to 32

image height set to 180 and 

image width set to 180

## Splitting the Dataset into Training and Validation

The data is split into training and validation

Training set is given 80% of the data and 

Validation set is given 20% of the data

## Classes

The dataset is classified into two classes based on the images.

The first class is of diseased crops' images and 

The second class is of healthy crops' images as shown below

![Screenshot 2022-12-20 121508](https://user-images.githubusercontent.com/78556152/208629407-e4b4ee16-2afc-4105-8bf8-653d3e49abf0.png)

Below are some images from the training dataset

![Screenshot 2022-12-20 121804](https://user-images.githubusercontent.com/78556152/208630043-dd56c4ec-99a8-4db3-99ed-86f6d573fce0.png)

![Screenshot 2022-12-20 121958](https://user-images.githubusercontent.com/78556152/208630440-3d51bf24-a8e5-4c64-8fc5-676dcebced2f.png)

## Keras Model

The dataset is configured for performance with two functions

data.cache() and 

data.prefetch()

The RGB channel values are standardized to [0,1] range by the use of tf.keras.Rescalling

A Keras model is created and compiled. Below is the summary of the model
![Screenshot 2022-12-20 122640](https://user-images.githubusercontent.com/78556152/208631986-b1f35434-76a8-4171-b3cb-058cc6819566.png)


## Training the Model

The model is then trained for 10 epochs as shown below

![Screenshot 2022-12-20 123010](https://user-images.githubusercontent.com/78556152/208632788-4e1a3fbb-8406-48f5-ba72-ec6e66c6290b.png)

The results are remarkable as seen with the training and validation accuracies having good values

## Visualize Training Results

Plots on accuracy and loss for training and validation sets are created and below are the results
![Screenshot 2022-12-20 123558](https://user-images.githubusercontent.com/78556152/208633969-f949f08a-f7b1-4e56-92f9-e40e6149a82a.png)

It is evident by the closeness of the margin between the training and validation accuracies that the model fit well.

I addition to that, it is also evident that the accuracy values are high, that is, at 0.94 and above. This is indicates that the model learned well.

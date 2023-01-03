# Cotton-Plant-Disease-Detection
A deep learning project for cotton plant disease detection using tensorflow

It mainly focus on the diseases which occurs only on leaves. However, more research is done on diseases that occur on stem, flowers buds and boll.

The diseases identified by this model are:

  . Diseases caused by aphids,
  
  . Diseases caused by army worms,
  
  . Bacterial Blight,
  
  . Powdery Mildew and
  
  . Target sport.

The data used in this project contains images of all the 5 types of diseases listed above including those of healthy leaves for comparison with the diseased ones.

Below is an example of a healthy cotton plant's leaf:

![sample-healthy-leaf](https://user-images.githubusercontent.com/78556152/210360017-06e7a605-2214-4074-9584-160850d47bcd.png)


## Defining some parameters for the loader

Batch size is set to 32

image height set to 180 and 

image width set to 180

## Splitting the Dataset into Training and Validation

The data is split into training and validation

Training set is given 80% of the data and 

Validation set is given 20% of the data

## Classes

The dataset is classified into six classes based on the plant's images of different diseases and the healthy ones.

This classes include; Aphids, Army Worms, Bacterail Blight, Healthy leaf, Powdery Mildew and Target Spot.

The image below shows the classes of the dataset:

![Screenshot 2023-01-03 155358](https://user-images.githubusercontent.com/78556152/210361283-94b2de53-76cf-4787-9a65-75ea18eee1f7.png)


Below are some images from the training dataset

![sample_training_diseases_images](https://user-images.githubusercontent.com/78556152/210361611-af3d4977-5c15-4e4f-b591-4f690e390244.png)


## Keras Model

The dataset is configured for performance with two functions

data.cache() and 

data.prefetch()

The RGB channel values are standardized to [0,1] range by the use of tf.keras.Rescalling

A Keras model is created and compiled. Below is the summary of the model

![Screenshot 2023-01-03 160123](https://user-images.githubusercontent.com/78556152/210362238-563e08ef-4545-4875-9a9f-444dacb6e0ce.png)

## Training the Model

The model is then trained for 10 epochs as shown below

![Screenshot 2023-01-03 161615](https://user-images.githubusercontent.com/78556152/210364558-340c558f-74d9-4082-9a4d-dd564fa465a6.png)


The results are not remarkable with validation accuracy being only 0.6170 despite training accuracy being 0.9895

## Visualize Training Results

Plots on accuracy and loss for training and validation sets are created and below are the results
![Screenshot 2022-12-20 123558](https://user-images.githubusercontent.com/78556152/208633969-f949f08a-f7b1-4e56-92f9-e40e6149a82a.png)

It is evident by the closeness of the margin between the training and validation accuracies that the model fits well.

In addition to that, it is also evident that the accuracy values are high, that is, at 0.94 and above. This indicates that the model learned well.

## Predicting on New Data

When an new image is tested for prediction, the model accurately put's it in the right class as shown below.

![Screenshot 2022-12-20 145253](https://user-images.githubusercontent.com/78556152/208661073-d50854f3-93c0-4ab4-b078-83d64a6f0388.png)

## Save model

The model is saved then served with tensorflow serving in docker during deployment.
![Screenshot 2022-12-20 145612](https://user-images.githubusercontent.com/78556152/208661539-789ce0ae-6148-4c56-9e76-87dc64a517d9.png)


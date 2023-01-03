# Cotton-Plant-Disease-Detection
A deep learning project for cotton plant disease detection using tensorflow

It mainly focus on the diseases which occur only on leaves. However, more research is done on diseases that occur on stem, flowers, buds and boll.

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

![training_and_validation_accuracy_and_loss_1](https://user-images.githubusercontent.com/78556152/210365383-57cdef02-3f4a-4e15-ae72-639fc8a1bcea.png)

From visualizing the training results above, the training accuracy is high but the validation accuracy is very low. The same applies to loss; the training loss is lower than the validation loss.

This shows that the model did not fit well causing a problem of overfitting that resulted into huge margins between training and validation results.

Some measures are taken to solve the overfitting problem below.

## Solving the problem of Overfitting

Two methods are used to solve overfitting:

  1. Data Augmentation- this creates modified copies of the dataset using existing data to artificially increase the training set.
  2. Dropout - This is a layer that randomly sets input units to 0 with a frequency of rate at each step during training time, which helps prevent overfitting.

Below is an example of augmented images:

![sample_augmented_images](https://user-images.githubusercontent.com/78556152/210369044-61e52e36-b7f1-4b65-aa41-325d998cc47a.png)

The code snippet below shows a new model with a dropout layer

![Screenshot 2023-01-03 164714](https://user-images.githubusercontent.com/78556152/210369702-e78e45e3-4631-4d37-90db-e6c027b56293.png)

## Training the New Model and Visualizing the Training Results

The new model trains with remarkable results. The training accuracy is 80% and the validation accuracy is 70%.

Plotting a graph of Accuracy and loss, the training and validation results are closer to each other indicating that the model fit well as shown in the image below.

![training_and_validation_accuracy_and_loss_2](https://user-images.githubusercontent.com/78556152/210370737-6f5a82f5-940e-4967-bce5-50fe9d4780c5.png)

## Predicting on New Data

A new image is given to the model for prediction, the model predicts the image's class with a high degree of accuracy and confidence.

![Screenshot 2023-01-03 165756](https://user-images.githubusercontent.com/78556152/210371600-4312f7ec-f235-4b6e-8a2e-6e9bd4ee9fcc.png)

## Saving the Model and Serving it with tensorflow serving

The model is saved and served with tensorflow serving in docker during production.

![Screenshot 2023-01-03 170143](https://user-images.githubusercontent.com/78556152/210372276-feb6398c-df68-4d29-b5bc-2ac565c5db47.png)

## Conclusion

There are a lot of crop diseases that affect different crops. In this project I focused on those that affect cotton plant specifically on the leaves. This model has done a good job of training and classifying images of five diseases that affect leaves of a cotton plant after which it can then detect a disease if new data is given to it based on those five classes of diseases. I can conclude that it is very possible to train a deep learning model to detect different types of crop diseases when given enough data to train on.

# Smoke and Fire Classification in Deep Learning

Hello guys, In this tutorial we are going to learn about new convolution neural network project. The project is smoke and fire classification using the convolutional neural network in deep learning. So I have implemented this project using the following steps like :

Import required libraries (tensorflow, numpy, keras, os etc).
Data Preprocessing (Data Augmentation) => Data Augmentation is basically used to generate multiple images from a existing image Like if we have a single front side image, so we can generate more image from it like we can generate rotation image, horizontal flip image, vertical flip image, increase zoom range of image. It perform to make a model prediction more accurate.
 Define our own cnn architecture. 
Train model. 
Evaluation.
Test a model.
CNNs are powerful image processing, artificial intelligence (AI) that use deep learning to perform both generative and descriptive tasks, often using machine vison that includes image and video recognition, along with recommender systems and natural language processing (NLP).

So i have implemented a Smoke and Fire Classification model using the CNN architecture. It can classify that the given image contains the smoke or fire and based on the image , it gives a result. I have defined my own CNN architecture and train my model only for two epochs and in only two epochs, it gave me 96% accuracy on the training data and 99% accuracy on the validation data which is really amazing.

NOTE : If you are going to train a cnn model on any dataset like If you are going to train model on cat dataset and You have a 1000 cat images in training and 100 cat images in validation. And suppose 40 dog images, 50 fox images are mixed with your training data and when you will train your model. So it may be happen that your model give 90% accuracy or above. But your model didn't train on good or you can say that clean data. And if you test this model on cat. So it perform well but if you will give dog or fox image to test, So it also classify cat. So note this point that if you have a good or perfect dataset, so your model will give better accuracy as well as better testing result.


# About Dataset
Wildfires are an important phenomenon on a global scale, as they are responsible for large amounts of economic and environmental damage. These effects are being exacerbated by the influence of climate change

It is important to detect fire and warn the people in charge. So you can create Smoke and Fire Detection Algorithms by using this dataset.

In this dataset, You will get 4 folders:

1. test_big

2. test_small

3. train-smoke

4. train_fire



So this is a imbalanced dataset. So we'll use only train-smoke and train_fire to train our model. Total 13,733 images in both folders. So we divide data into 90:10 ratio. 12,360 images for train and 1373 images for validation.


# Let's start :-
So now let's start the Smoke and Fire Clssification project. So first of all we import some required libraries for data preparation like os shutil etc. Next step is to remove the warnings. Now it's time to prepare the dataset, so firstly create a smoke and fire dataset folder, then move our training fire and smoke dataset folder into our created folder with the name Fire and Smoke and delete the test_big and test_small folder. Now import the library for the data preprocessing.

Now performed the data preprocessing, firstly define the training path, then perform the data preprocessing (Data Augmentation), Data Augmentation it basically used to create multiple images from a single image like if we have a 10 cat images, so it creates many images from 10 images. It rotate of 10 cat images, horizontally flip of 10 images, vertical flip of 10 images, increase zoom range of 10 images etc. It perform to make a model prediction more accurate. After performing data preprocessing we got our indices, 0 stands for fire and 1 stands for smoke. And it's a binary classification problem which will give result of the given image in the form of 0 or 1.

# Architecture of my own CNN
→ Sequential model

→ 1 x convolution layer of 32 filter size and same padding and activation function will be relu(Rectified Linear Unit) and input_size is 224x224x3.

→ 1 x maxpool layer of 2x2 pool size and 2x2 stride 

→ 1 x convolution layer of 64 filter and same padding and activation function will be relu(Rectified Linear Unit)

→ 1 x maxpool layer of 2x2 pool size and 2x2 stride 

→ 1 x convolution layer of 256 filter and same padding and activation function will be relu(Rectified Linear Unit)

→ 1 x maxpool layer of 2x2 pool size and 2x2 stride 

Basically relu activation function apply to each layers so that all the negative values are not passed to the next layer.

After implementing all the convolution layers then I flatten the data into vectors which comes out of the convolutions and I passed the data to the dense layer.

→ 1 x Flatten layer  

→ 1 x Dense layer of 128 units and activation function will be relu(Rectified Linear Unit)

→ 1 x Dense Softmax layer of 1 units and activation function will be sigmoid. Sigmoid activation function is used when we have a binary classification problem

Now check the summary of a model and Now compile the model and train the model only for two epochs and in only two box I got 96% accuracy on the training data and 99% accuracy on the validation data. And I test model is working accurate on the test data.

Then evaluate the model revolution is basically used check the validation accuracy. Then save my model with the extension .h5 and load a model with function load_model(path of model).

Define my test function for test the model. So firstly import required libraries for the testing then defined my function. In this function, firstly I load a image then convert image into array, then rescale the image, then expand the dimension, then simply predict the model with the predict_classes(image) function.

Now it's time to use the function, firstly I gave 2 fire images and test my model on that images and you can see in the below image that it classifies fire images correctly.
Now I gave 2 smoke images and test my model on that images and you can see in the below image that it classifies smoke images correctly.


#NOTE
If you have a gpu based laptop, then you can run .ipnyb file in local system. Otherwise you can use the Google Colab which provides a faster gpu for train a model faster.


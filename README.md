North American Bird Species Identification 
A project training a ResNet50 model to recognize 50 different species of birds

## Overview 
This project aims to train a machine learning model capable of accurately identifying between 50 common North American bird species from a dataset of 40-50 images for each species, using 4 images each for testing and validation. 


## Dataset 
The project utilizes a dataset organized in folders for several North American bird species. The dataset is organized into training, validation, and test sets. Each subdirectory within these sets corresponds to a specific bird species, with images of that species stored within. 

**Data Acquisition:** 
50 species were selected from a 200 species dataset from Kaggle and uploaded to Google Drive for use by a notebook run on Colab

**Data Preprocessing:** 
To prepare the data for uptake, folders for testing and validation were created.  Once created, these folders were filled by running a jupyter notebook with Nutcracker, a function created to take the first 4 images of a dataset, place them in the training folder, then the last 4 images in the validation folder.
Before being fed into the model, the images are resized to (299, 299, 3) or squares of 299 pixels and 3 colors


## Model Architecture 
The ResNet50 convolutional neural network (CNN) was chosen for this project.
ResNet-50 is a well-established CNN developed by Microsoft and known for its ability to learn complex features from images and effectiveness in image classification tasks. Weights from imagenet are used for transfer learning with the goal to reduce the number of epochs (and amount of Google Colab credits used). The final layer of the model is adapted to match the number of bird species in our dataset. 


## Training 
The model is trained using the training dataset and evaluated periodically on the validation dataset to monitor performance and prevent overfitting. 

**Training Procedure:**
A dataset containing 35-40 images for each species for training was used, with an additional 4 images each for testing and validation.  The data was trained using the ResNet50 model for 30 epochs. 

**Optimization Algorithm:** 
Adam was selected as the optimization algorithm. 

**Loss Function:** 
Categorical Cross-entropy was selected as the loss function.

**Learning Rate Schedule:**
The learning rate was set at 0.001 and did not change over the course of the training.

**Hardware Used:**
Google A100 GPU units were used to perform the training.  When not available, Google L4 GPU units were used.


##Additional Code
2 additional notebooks are included as described below:

**Populate train and validation data**
This contains a function (nutcracker) where the user sets the training folder and destinations for the test and validation images.  This function seatches for subfolders and for each subfolder in the training folder, it takes the first 4 images and places them in the aproprate test subfolder and the last 4 in the folder for validation.

**Rotate images**
In case more training data is needed, a function to loop through a folder and make copies of each image rotated a specified amount of degrees was created.  This function (oystercatcher) takes the target file and degrees to rotate the images as inputs. 

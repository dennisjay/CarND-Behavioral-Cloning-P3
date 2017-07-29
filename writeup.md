#**Behavioral Cloning** 

##Writeup

---

**Behavioral Cloning Project**

The goals / steps of this project are the following:
* Use the simulator to collect data of good driving behavior
* Build, a convolution neural network in Keras that predicts steering angles from images
* Train and validate the model with a training and validation set
* Test that the model successfully drives around track one without leaving the road
* Summarize the results with a written report


[//]: # (Image References)

[image1]: ./examples/placeholder.png "Model Visualization"
[image2]: ./examples/placeholder.png "Grayscaling"
[image3]: ./examples/placeholder_small.png "Recovery Image"
[image4]: ./examples/placeholder_small.png "Recovery Image"
[image5]: ./examples/placeholder_small.png "Recovery Image"
[image6]: ./examples/placeholder_small.png "Normal Image"
[image7]: ./examples/placeholder_small.png "Flipped Image"

## Rubric Points
###Here I will consider the [rubric points](https://review.udacity.com/#!/rubrics/432/view) individually and describe how I addressed each point in my implementation.  

---
###Files Submitted & Code Quality

####1. Submission includes all required files and can be used to run the simulator in autonomous mode

My project includes the following files:
* Behaviour_Cloneing.ipynb containing the script to create and train the model
* drive.py for driving the car in autonomous mode
* model.h5 containing a trained convolution neural network 
* writeup_report.md or writeup_report.pdf summarizing the results

####2. Submission includes functional code
Using the Udacity provided simulator and my drive.py file, the car can be driven autonomously around the track by executing 
```sh
python drive.py model.h5
```

I did not change anything in the drive.py file, because the preprocessing of input is done within the model.


####3. Submission code is usable and readable

The Behaviour_Cloneing.ipynb model.py file contains the code for training and saving the convolution neural network. The file shows the pipeline I used for training and validating the model, and it contains comments to explain how the code works.

###Model Architecture and Training Strategy

####1. An appropriate model architecture has been employed

The model consists of the pretrained VGG-16 layers with imagenet weights. The classification part is replace by one 1024 neuron Dense-Layer with "relu"-Activation, followed by 3 smaller Dense Layers without an activation function.

####2. Attempts to reduce overfitting in the model

I did not consider any overfitting so I didn't apply any dropout or regularizers.

####3. Model parameter tuning

The model used an adam optimizer, so the learning rate was not tuned manually (model.py line 25).

####4. Appropriate training data

At the end I decided to use only the udacity dataset, because my datasets were made with the keyboard. When using my own data I got much higher training and validation loss.

###Model Architecture and Training Strategy

####1. Solution Design Approach

At the beginning I tried to apply three flattend Dense Layers. This approach was not perfoming very well so I decided to use the VGG-16 net as a base.
####2. Final Model Architecture

The final architectur consists of a VGG-16 model as a Base and a 1024-Neuron dense layer with ReLU-Activation.  


####3. Creation of the Training Set & Training Process


I the end I used the training data given by udacity because my own training data didn't perform very well.
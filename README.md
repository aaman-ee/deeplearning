![Alt text](http://i.imgur.com/geLD4Xh.jpg)
---
Welcome to deep learning workshop for the complete end-to-end pipeline for real-time DL applications.

During this workshop, you'll learn the complete process for training and deploying efficiently CNNs using the state-of-the-art research tools.

### Table of Contents

* [What do you need (S/W & H/W)?](docs/prerequisites.md)
* [Understanding your Problem/Application](#understanding your problem/application)
* [Preparing your Training Data](#preparing-your-training-data)
* [Train you network]
* [Deploy your network]
    * [Low power devices]
* [Things to have in mind]

## Understanding your Problem/Application

It is very critical to unserstand the principles of the application you want to build, otherwise you will later face possible delays for re-training and re-preparation of your traninng data. In several cases, a not clear understanding would mean CNN generalization failure, since false pre-trained CNNs were used for your final trained model. 
A good way to start is to identify the desired output of your CNN. 
After an image input, the trained CNN should:

*Identify a certain (single class) pattern/object?*<br>
*Identify multiple (multi-class) patterns/objects?*<br>
*Detect (identify and locate) a certain (single class) pattern/object?*<br>
*Detect (identify and locate) miltiple (multi-class) patterns/objects?*<br>

Based on each selection, the format of the training dataset and the output layer of the CNN have to be precisely defined.
When we want to identify, the CNN structure is often called *imageNet* <sub>(not to be confused with the [ImageNet database](http://image-net.org/))</sub><br>
When we want to detect, the CNN structure is often called *detectNet* <br>
For an *imageNet*, the training set includes only images and the respective correct classes<br>
For a *detectNet*, the training set includes images, the respective correct classes, and their bounding box coordinates<br>

For a single-class imageNet, (i.e. identify lemons in an image) the output for the following query image would be a single number denoting the probability of the image showing a lemon. 

<img src="https://raw.githubusercontent.com/aaman-ee/deeplearning/master/docs/lemon.png" width="500"/>

For a multi-class imageNet, (i.e. 1000 classes) the output for the following query image would be several numbers denoting the probability of the image showing several certain classes. 

<img src=https://raw.githubusercontent.com/aaman-ee/deeplearning/master/docs/lemonandwoodgrain.png width="545"/>

For a single-class detectNet, (i.e. identify and detect lemons in an image) the output for the following query image would be a box around the object. 

<img src=https://raw.githubusercontent.com/aaman-ee/deeplearning/master/docs/detectNetlemon.png width="710"/>

Finally, for a multi-class detectNet the output could be something like the following.

<img src=https://raw.githubusercontent.com/aaman-ee/deeplearning/master/docs/detectNetlemonandwoodgrain.png width="710"/>

Since the output of the CNN is different for each case, it is clear that apart from the output layer of the CNN, the training dataset must be provided  in the correct and respective format.<br>
More details on the training set construction are discussed in the next Section.

## Preparing your Training Data

During the turotial we will comply with the DIGITS standard for the Training Data structure, howerver, this structure is used almost in most DL frameworks.

###imageNet
For a multi-class imageNet, the general rule is to inlcude images of each class in a separate subfolder and one file for the labeling of all images. <br>
The folder structure that must be followed is described [here](https://github.com/NVIDIA/DIGITS/blob/master/docs/ImageFolderFormat.md) clearly.
For selecting validation and testing sets, you have two options. Either prepare a new folder with the same structure, or Import all your images and labels and select the percentage for testing and validation throught the DIGITS interface. In the latter case, DIGITS will select randomly a portion from each class for the test and validation image sets.  
<img src=https://raw.githubusercontent.com/aaman-ee/deeplearning/master/docs/trainval.jpg width="710"/>

For some widely used datasets (MNIST, CIFAR), python scripts are available [here](https://github.com/NVIDIA/DIGITS/blob/master/docs/StandardDatasets.md).

###detectNet
For multi-class detectNet, for each training image, a separate accompanying txt file is needed. The folder structure remains the same, but the labeling format is more detailed. The DIGITS framework, follows the KITTI database labeling format which can be found [here](https://github.com/NVIDIA/DIGITS/blob/master/digits/extensions/data/objectDetection/README.md).

After reading carefully the labelling format, we should note that certain labeling values are not necessary for several applications. Only the data which is actually needed for the particular application should be used. If two or more objects are located in the same image, new lines in the coresponing txt file are added.


![Alt text](http://i.imgur.com/geLD4Xh.jpg)
---
Welcome to deep learning workshop for the complete end-to-end pipeline for real-time DL applications.

During this workshop, you'll learn the complete process for training and deploying efficiently CNNs using the state-of-the-art research tools.

### Table of Contents

* [What do you need (S/W & H/W)?](docs/prerequisites.md)
* [Understanding your problem-application](#understanding-your-problem/application)
* [Prepare your training data]
* [Train you network]
* [Deploy your network]
    * [Low power devices]
* [Things to have in mind]

## Understanding Your Problem/Application

It is very critical to unserstand the principles of the application you want to build, otherwise you will later face possible delays for re-training and re-preparation of your traninng data. In several cases, a not clear understanding would mean CNN generalization failure, since false pre-trained CNNs were used for your final trained model. 
A good way to start is to identify the desired output of your CNN. 
After an image input, the trained CNN should:
**Identify a certain (single class) pattern/object?
**Identify multiple (multi-class) patterns/objects?
**Detect (identify and locate) a certain (single class) pattern/object?
**Detect (identify and locate) miltiple (multi-class) patterns/objects?

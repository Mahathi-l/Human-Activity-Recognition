# Human-Activity-Recognition

Humans naturally develop walking capability that is energy efficient, stable, environment adaptive, and robust. Lower limb amputations,
unfortunately, disrupt this ability; individuals with lower limb amputations usually depend on prosthetic devices to restore the basic
walking function. Lower-limb robotic prosthetics can benefit from context awareness to provide enhanced comfort and safety to the
amputee. In this work, we aim to develop a terrain identification system based on inertial measurement units IMU streams collected
from the lower limb. The system for a prosthetic leg uses visual and inertial sensors though, but we are willing to observe if terrain
identification without the visual data is viable. With such information, the control of a robotized prosthetic leg can be adapted to changes
in its surrounding.

Types of terrains
This is a classification task to find different terrains from time series data. The idea is to train a neural network using given data to
classify which terrain an unknown data represents. We will use F1 score as the evaluation metric for this project

Here is a brief description of the data:

  - "_x" files contain the xyz accelerometers and xyz gyroscope measurements from the lower limb.
  - "_x_time" files contain the time stamps for the accelerometer and gyroscope measurements. The units are in seconds and the sampling rate is 40 Hz.
  - "_y" files contain the labels. (0) indicates standing or walking in solid ground, (1) indicates going down the stairs, (2) indicates going up the stairs, and (3) indicates walking on grass.
  - "_y_time" files contain the time stamps for the labels. The units are in seconds and the sampling rates is 10 Hz.


The data set is imbalanced. Here are some suggestions for handling imbalance:

  1. Make sure you create a validation set that is also balanced in order to better represent the type of testing data you will get.
  2. You can modify your loss function to include weights that compensate for the imbalance distributions. A quick search online would give you some hints on how to do this.
  3. When doing data augmentation, you can make sure your training data is balanced by getting more replications (with some deformation / noise) for those classes that have fewer samples.
  4. You can also apply a subsampling approach when creating your batches which includes all the data for the smaller datasets but selects a smaller proportion from the classes with most instances (in order to keep the number per class about the same).

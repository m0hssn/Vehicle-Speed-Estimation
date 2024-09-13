# Vehicle-Speed-Estimation

[Dataset on github](https://github.com/commaai/speedchallenge)


## Overview

This project consists of several key components that focus on video frame extraction, optical flow computation, dataset preparation, and training a CNN-based regression model to predict velocity from video frames and optical flow data.


## Optical Flow Calculation

Optical flow is computed between consecutive frames to capture motion information. This is done using the Farneback method. The optical flow is visualized as images, theese images are then used for velocity prediction.


## Velocity Prediction

A CNN regressor is trained to predict vehicle velocity from the optical flow images and corresponding frames. The network uses a pretrained ResNet-50 model as the backbone for feature extraction and a custom fully connected layer for regression.


## Results 

The model achieves a training loss (MSE) of 1.36, but struggles to replicate this performance on the test dataset. Upon analysis, it was found that the training and test datasets had minimal overlap in terms of velocity ranges. The training data also had limited coverage of different speed ranges, which affected the model's ability to generalize effectively.


## Future Work

To improve the model's performance, the dataset could be augmented by modifying the frame rates. For instance, dropping frames between consecutive images could simulate different speeds, which would expand the range of velocities represented in the dataset. This would help the model cover a wider range of speeds, enhancing its ability to generalize to unseen data.

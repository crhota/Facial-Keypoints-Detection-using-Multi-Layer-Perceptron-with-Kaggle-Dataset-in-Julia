# Facial-Keypoints-Detection-using-Multi-Layer-Perceptron-in-Julia
This contains code and explanation behind the code for detecting 15# facial keypoints for a given face image using Multi Layer Perceptron in Julia.

## 1. Problem Statement / Objective
We need to detect the x,y coordinates of 15 keypoints of a given image of a face. There are 15 keypoints that need to be detected. Hence, 15x2 = 30 coordinates.Face image data is available as 9216 pixels corresponding to a 96x96 image.

We have training data for various face images and their respective keypoint coordinates. We need to train the model using this training data. As the input and output values are known, model will undergo thro **supervised machine learning**. Output here are keypoints where we need to predict the x,y coordinates - these are not various classes that we need to predict, rather  specific values that needs to be predicted. Hence, this is type of **regression problem**.

## 2. Intent
Intent of this project is to keep it simple and get a hands on experience of the elements starting from getting the data to predicting the output. Additional design of experiments for optimization, identified during the project has been summarized in the "**Further Work**" section.

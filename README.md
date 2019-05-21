# Facial-Keypoints-Detection-using-Multi-Layer-Perceptron-in-Julia
This contains code and explanation behind the code for detecting 15# facial keypoints for a given face image using Multi Layer Perceptron in Julia.

## 1. Problem Statement / Objective
We need to detect the x,y coordinates of 15 keypoints of a given image of a face. There are 15 keypoints that need to be detected. Hence, 15x2 = 30 coordinates.Face image data is available as 9216 pixels corresponding to a 96x96 image.
We have training data for various face images and their respective keypoint coordinates. We need to train the model using this training data. As the input and output values are known, model will undergo thro **supervised machine learning**. Output here are keypoints where we need to predict the x,y coordinates - these are not various classes that we need to predict, rather  specific values that needs to be predicted. Hence, this is type of **regression problem**.

## 2. Intent
Intent of this project is to keep it simple and get a hands on experience of the elements starting from getting the data to predicting the output. Additional design of experiments for optimization, identified during the project has been summarized in the "**Further Work**" section.

## 3. Gratitude
My sincere gratitude to my teachers for sharing the knowledge on Machine Learning and Julia:
- **Anandi Giridharan**, Principal Research Scientist, Electrical Communication Engg., Indian Institute of Science,Bengaluru, India
- **Dr. Vijaya Kumar B.P**, Professor & Head, Information Science & Engg., MS Ramaiah Institute of Technology, Bengaluru, India
- **Abhijith Chandraprabhu**, Application Engineer, Julia Computing, Bengaluru, India

I sincerely thank **Julia Slack Community** (https://julialang.slack.com) and **my batchmates of Jan-May'19 Computational Machine Laerning Course at CCE, IISc** for clarifying various doubts of mine which helped a lot at critical junctures of my learning.  

I am indebted to **my family** for providing me the support and space to spend time on learning new things.

## 4. Link to Data / Description of the available Data
Training and Test Data is available at following location: https://www.kaggle.com/c/facial-keypoints-detection/data <br>

**Training Data** <br>
- File Name/Type: **training.csv** <br>
- Each row corresponds to an instance. There are **7049 rows**. There has **31 columns**. <br>
- **Column 1 to 30** correspond to the x,y coordinates of the 15 keypoints. <br>
- **Column 31** has the face image data. There are **9216 pixel data**. Each pixel data is in the **range [0,255]**<br>

**Test Data** <br>
- File Name/Type: **test.csv** <br>
- Each row corresponds to an instance. There are **1783 rows**. There are **2 columns**. <br>
- Column 1 corresponds to image ID. <br>
- **Column 2** has the face image data. There are **9216 pixel data**. Each pixel data is in the **range [0,255]** <br>

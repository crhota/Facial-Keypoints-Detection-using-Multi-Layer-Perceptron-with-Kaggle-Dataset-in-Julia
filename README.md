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

## 5. Algorithm
Here is an high level explanation of the steps followed in building the model - key steps are listed below:
- Data Representaion <br>
- Network Topology <br>
- Network Parameters <br>
- Training <br>
- Validation <br>

### 5.1. Network Topology
CNN is recommended for this kind of applications. Intent currently is to build a simple end-to-end solution to so that I have understanding of the machine learning as well as Julia. Hence, I am chosing to **Multi-Layer Perceptron** as the network topology. ...**Further Work 2(a)**

### 5.2. Network Parameters
(9216 Pixel Image) **Input** -> **Model** -> **Output** (30 coordinates of the keypoints) <br>

**Number of Layers / Neurons**
- We need to have an input layer with 9216 neurons. <br>
- We need to have an output layer with 30 neurons. <br>
- To keep it simple, we are having 1 hidden layer with 100 neurons. ...**Further Work 3(a),3(b)** <br>

**Activation Function** <br>
- Input to Hidden Layer
  - We need non-linearity to be there for the input to the hidden layer. 
  - Input Values are pixel data and Output Values are keypoint coordinates. 
  - As both of there are non-negative, chosing the activation function as **ReLU**. f(x) = { 0 for x<0 ; x for x>=0 }
- Hidden to Output Layer
  - Output of the Hidden layer directly predicts the coordinates.
  - We do not wish to modify it in anyway. Hence, chosing the activation function as **Identity**. f(x) = x (for all x)

### 5.3. Data Representation
**Training Data - Input**
* We need to extract the Image Pixel Data from Column 31 for each instance(row).
* Image pixel data range is [0,255]. We need to divide each value by 255 to get the values in [0,1]
* We need to have the pixel data in a (9216,1) column vector (array format) - to match to the network input layer
* We need to have multiple above arrays corresponding to various instances in an array
**Training Data - Output**

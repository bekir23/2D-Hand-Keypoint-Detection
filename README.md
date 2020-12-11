# 2D Hand-Keypoint-Detection

* This project aim to detect hand joints. Model of this project utilize simple CNN architecture.

## Dataset

* Dataset Link: http://www.rovit.ua.es/dataset/mhpdataset/

## Project Steps

* Dataset will be consisting of images and 3D location coordinate files of the joints. You need to convert from 3D coordinates to 2D coordinates. Luckily, dataset publishers provided a conversion script. Script is named: 'generate2Dpoints.py'. You need to run this script and generate txt files for the 2D coordinates.

* Then, you need to generate the bounding box coordinate txt files. The relevant script for this task is named 'generateBBoxes.py'.

Note: 'generateBBoxes.py' and 'generate2Dpoints.py' scripts must run with python2. Because this script is written according to python2.

* Okay now.We have hand images,2D coordinates of the joints of the hand images and bounding box of the hand images. Let's get start to preprocess step.

### Preprocess Step
* We crop image  according to bounding box of the image and padding cropped image to fixed size. Because all images has different cropped size.
* Then joints of the hand images have to readjust according to cropped image.
* All images, joints and bounding box information save into dictionary in order to utilize in model step.

### Model Step
* Read dictionary that we save. Create CNN model that you want. Set test,train and validation dataset. Fit model and predict over test dataset.



## Result
#### Prediction Images  ---------------------------------------  Ground Truth Images
![Alt text](/images//example_1_prediction.JPG?raw=true "Exampe 1-Prediction")
![Alt text](/images//example_1_ground_truth.JPG?raw=true "Exampe 1-Ground Truth")

![Alt text](/images//example_2_prediction.JPG?raw=true "Exampe 2-Prediction")
![Alt text](/images//example_2_ground_truth.JPG?raw=true "Exampe 2-Ground Truth")

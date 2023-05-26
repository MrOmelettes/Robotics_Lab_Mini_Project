# RoboticsLab: Mini Project (Group 7)
### Group Members
640110098 - Krittapas Sithirungson 

64011359 - Chakrit Grittiyarangsan 

64011498 - Pachara Kongkasem

64011620 - Siripong Boonsiri

64011688 - Tycoon Suya

#

### Task 1: Data Acquisition
We would like our object detection project to detect some kitchen utensils.
We chose spoon, fork and knife which can be find easily in every household as the main label. 
After that we acquire the dataset for training the model by downloading .jpg images from a website. 
We mainly used [Unsplash](https://unsplash.com/) to acquire the dataset of images.
> We acquired 60 pictures in total. With 20 pictures for each label (spoon, fork and knife).

#

### Task 2: Data Preparation
We uploaded the pictures to [Roboflow](https://roboflow.com/) to annote the data. We used the auto-polygon tool for easier annotation.
We annote all image with labels which are spoon, fork and knife.
> Then we decided to split the data as follow. 80% Train 19% Validate and 1% Test

To make the dataset larger for better training, we decided to augment images to make more dataset by flip, crop, rotate, change HSV, cutout, shear, blur, create noise and make it grayscale.
> The end result of augmentation is that we recieved 1028 images for the dataset.

#

### Task 3: Model training and deployment
We decided to train our model using [Google Colab](https://colab.research.google.com/) because it can boost training process with the T4 GPU.
To trained the model using Yolov5, we clone the Yolov5 to the google drive directory.
We also changed the data.yaml to configure the train-test-split images folder path.
After that we trained the model using train.py included with Yolov5 for 100 epochs.
> The result after training and validation is as follow.
>
> 1. Precision : 0.45
> 2. Recall : 0.379
> 3. mAP50 : 0.384
> 4. mAP50-95 : 0.196

Before deploying the model to NVIDIA Jetson Nano, we also tried making our model detect an object usimg the images from the test folder.
We then save the best.pt which is our model and put it in our SD card.

#

### Task 4: Model Inference
We prepare necessary hardware for this mini-project which include the NVIDIA Jetson Nano, a monitor, a keyboard, a mouse, a camera, a LAN cable and a powercable.
Then we connected them all together.
We setup the Jetson Nano before deploying the trained model by installing an OS in it, install Python3 and install necessary libraries for Yolov5.
After that we run the detect.py with the source is 0 which is the camera connected to the Jetson Nano and the model is our best.pt file.

#

To see our whole working process video please click on this [YouTube link](https://www.youtube.com/watch?v=As73PzF3a9E).

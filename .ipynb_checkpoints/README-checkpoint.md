# Introduction

This is Face Recognition web application developed using Flask API. The application have three main modules which are: 

1. The Registration Module
2. The Training module
3. The Recognition module

The flow of the application is something like:

- A user is first registered with either of the following two ways. First, by choosing his images which are stored somewhere locally. Second, a user can be registered by running live webcam in case he's present physically. The camera will take specified number of images and register the person.

- After taking photos of a user to be regisrered, the classifier is trained on the data.
- Finally we are able to recognise the registered person by clicking on the recognise button which will open webcam.

The code uses face_recognition api. The Github link for the api is given below:

https://github.com/ageitgey/face_recognition
resize_scale
# How to set up the Environment:

Before you run the code, you would need to install the some packages mentioned in the requirements.txt. You can simply run the following command while in the project direcotory.

    pip install -r requirements.txt

Make sure that you have dlib installed already in your PC. To install dlib, you would need to install Visual Studio build tools which can be done as follows:

- Download Visual Studio installer from the link here: https://visualstudio.microsoft.com/downloads/

- Run the installer and under Workloads tab, select Desktop Development with C++. Make sure to check MSVC build tools and leave everything as default as shown in the figure below. Click Install and download.
![Visual Studio Installter](screenshots/VS_Installer.png)

- Then install dlib by running the following command:

        pip install dlib

Once you install dlib, you will then be able to install face_recognition api from the link given above.


# How to run the code:

The code can be run with cmd command with some flags to specify which are user's choice. The flags description are:

- **--threshold:** Probability threshold above which a person is to be classified, else unknown, default is 0.7.
- **--training_images:** # of images required to train the classifier on, greater number brings better accuracy, default is 10.
- **--gpu:** Specify whether to use GPU, default is False.
- **--distance_threshold:** How much distance between faces to consider it a match. Lower is more strict. 0.5 is typical best performance.
- **--resize_scale:** Resize the input video, e.g. 0.75 will resize to 1/4th of the video. default is 1 means No resize.

A sample command for videos can be like:

    python run.py --threshold=0.7 --training_images=10 --gpu --resize_scale=0.75

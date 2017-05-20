# **Implemented a software pipeline to identify the fine-tuned lane boundaries in a image and video**

This is a project for Udacity Self-Driving Car Nanodegree program. In this project I implemented algorithm to find the advanced lane line in an image and video, using OpenCV techniques which include camera distortion correction, lane detection with color channel, Sobels' edge detection, estimation of lane curvature/vehicle position. The model is implemented in the file `Advanced_Lane_Lines_RYANKANG.ipynb `. 

## Requirement 

- Python > 3.5.0
- OpenCV Library

## Run the Project 

Run the `Advanced_Lane_Lines_RYANKANG.ipynb ` on the ipython notebook. You can use images of "camera_cal", "test_images" folder and video file of "project_video.mp4" for this project.  

## About the Project 

I built the software pipeline with below steps: 

1. Compute the camera calibration using chessboardimages and undistort test images. Below image is undistored test image:
![Test image](https://github.com/KHKANG36/Advanced_Lane_Line_Finding-Project/blob/master/output_images/Undistorted_Test2.jpg)
2. Identify the lane line using sobels' edge detection algorithm and RGB/HSV color channel. Below is detected binary image:   
![Test image](https://github.com/KHKANG36/Advanced_Lane_Line_Finding-Project/blob/master/output_images/Threshold_binary_Test2.jpg)
3. Conduct perspective transform for the test image to identify the curvature of the lane. This is the result image of transform:  
![Test image](https://github.com/KHKANG36/Advanced_Lane_Line_Finding-Project/blob/master/output_images/Warped_binary_Test2.jpg)
4. Find the pixels information using sliding window technique and calculate the curvature of the lane with polynomial fitting
5. Plot back down onto the road image by reverse perspective transform based on curvature information of the lane line
![Test image](https://github.com/KHKANG36/Advanced_Lane_Line_Finding-Project/blob/master/output_images/Warped_back_Test2.jpg)
6. Apply the pipeline to video stream. Use the several previous frame information to prevent jitter, and make robust detection

More detailed explanation for the project is written on "writeup_RYANKANG.pdf" file. 

## Discussion/Issues 

1. Finding optimal source/destination point for perspective transform. 
2. Need to more robust algorithm at challenging driving environment such as a lot of trees, shadows, light reflection, road pavement

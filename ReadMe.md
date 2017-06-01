# **Finding Lane Lines on the Road** 

## Writeup Template

This write up contains the explanation of the project
---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Make the LAN Detection alogorithm test on both Images as well as for Video Output


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Project Pipeline 
My pipeline consisted of 5 steps. First, I converted the images to grayscale using the open CV, then I have used the Gaussian Noise reduction to remove the
noise from the images. As the third step, I used the canny edge detection algorithm to detect the edges in the images. I have abstracted a Quadrilateral which will be defined
the region of the lane lines in the image which will be of our use. Future to find exact lines in the images based on points, I have used Hough Line open CV algorithm to detect lines in the image.
To draw the lines finally, I have made draw_lines functions which will calculate the slope of the lines and detect the left and right lines based on the 
+ve or -ve slope. I have taken the mean of all the slopes and then use the cv2.line to finally draw the lines with Weighted function.

My LAN Detection algorithm can further be used LAN Detection in Videos as the video is just the series of images, so individual frames have to pass via this final_image function and LAN detection will happen. 

### 2. Potential shortcomings in my current pipeline


One potential shortcoming would happen while taking the mean. As I am using the mean of the coordinates, it may happen the lines not come correctly with large outputs as there will be deflection. 

### 3. Possible improvements in my pipeline

A possible improvement would be to include linear regression to find out the points in the Hough Line output to find exact line points.

Another potential improvement could be to include a shape for the region of interest based upon a shape that can be scale across.  
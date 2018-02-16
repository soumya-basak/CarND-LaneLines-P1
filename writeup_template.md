# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of several steps. First, I converted the images to grayscale, then I applied Gaussian Smoothing, Canny Edge,and Hough transformation Line Detection. the goal is to piece togather all the pipeline to detect the line segment in the image. Then avarage/extrapolate them and draw them into the image for display.

In order to draw the algorithm I used the following techniques:
Transform RGB to Grayscale, apply Canny Edge Detection and Applies an image mask, Only keeps the region of the image defined by the polygon formed from `vertices`. The rest of the image is set to black, and final pipeline will bedraws `lines` with `color` and `thickness` Lines are drawn on the image inplace (mutates the image).



### Test Images 
Please look into the ipython notebook: 
https://github.com/soumya-basak/CarND-LaneLines-P1/blob/master/P1.ipynb

### 2. Identify potential shortcomings with your current pipeline

1. It would not work if the camera angle would be different and the ROI will be different.
2. It would not work if the colour of lane will be different and canny edge transform will not work
3. It would not work if something like car, people or animal into the street, and messup extrapolate of the lane.  


### 3. Suggest possible improvements to your pipeline
1. Parameter can be tweaked even better performance.
2. If there is a abrupt changes between two frames, we can reject the result of the second frame because it does not make scense. 

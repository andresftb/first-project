# **Finding Lane Lines on the Road** 

## Writeup Template

### This project was done for the Udacity Nano Degree Self Driving Car Program.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report




---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, second I applied the Gaussian Noise kernel to find the blur image. The third step was to apply the canny function to find the edges of the lanes. In the forth step I applied the Hough transform. The fifth step was to draw the lines. 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by separating the line segments by their slope ((y2-y1)/(x2-x1)) to decide which segments are part of the left line vs. the right line. Then I did a linear regression with respect of the top and bottom points of the image to find the best fit line for the lanes.

If you'd like to include images to show how the pipeline works, here is how to include an image: 

<img src="Withline right.png" width="480" alt="Combined Image" />

<img src="YellowLine.png" width="480" alt="Combined Image" />

### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be that small segments of the curve are taking into account, which makes my prediction diverge. 

Another shortcoming could be the noise generated by these approche. 


### 3. Suggest possible improvements to your pipeline

Doing my research I find a posible solution that is based on the feedback of the calculation of the target slope from every frame.

https://medium.com/@esmat.anis/robust-extrapolation-of-lines-in-video-using-linear-hough-transform-edd39d642ddf


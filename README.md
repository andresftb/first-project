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

My pipeline consisted of 5 steps. First, I converted the images to grayscale, second I applied the Gaussian Noise kernel to find the blur image. The third step was to apply the canny function to find the edges of the lanes. In the forth step I applied the Hough transform. The last and fifth step was to draw the lines. 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by separating the line segments by their slope ((y2-y1)/(x2-x1)) to decide which segments are part of the left line vs. the right line. Then I did a linear regression with respect of the top and bottom points of the image to find the best fit line for the lanes.

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

Doing my research I find a posible solution that includes feedback


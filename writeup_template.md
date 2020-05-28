# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./grayscale.jpg "Grayscale"

---

### Reflection

### 1. Pipeline Description

My pipeline consisted of 5 steps:
1) Convert the image to grayscale.
2) Use Gaussian Blur to smooth the grayscaled image (with kernal 5).
3) Use Canny algorithm to find edges (with thresholds from 50 to 150).
4) Get the region of interest of trapezium shaped with 4 vertices.
5) Use Hough Transform on the masked image and weight the final output.

In order to draw the two lane lines (left and right), here are the steps:
1) Separate detected line segments with equation y = mx + b into left and right lane lines by calculating line slope m and value b. Positive slope is left lane line and negative slope is right lane line.
2) Calculate the average m value and b value within each list of left lane and right lane.
3) Draw two lines with y values of bottom and top of trapezium mask using the average m and b above. Those are two desired lane lines.

[image1]: ./test_result.png "Test Image"


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...

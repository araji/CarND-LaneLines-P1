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

Following at the different parts of the pipeline:
    -  apply canny to the greyed out images to extracts edges
    - define region of interest area from which will extract lines
    - apply Hough transform to the region of interest .
    - split the lines output of the hough transform based on their slope to map them to either left or right lane.
    - average out the slope on each lane to generate the right and left lanes.
    - generate a new image by overlaying the result two lanes over the original image.

### 2. Identify potential shortcomings with your current pipeline

- very sensitive to camera/lane position
- not smooth as in a  lot of variance from one frame to the other
- will fail miserably in curved lane situation
- will fail miserably in bad weather /night situation

### 3. Suggest possible improvements to your pipeline

    -   dynamically find both Hough and Canny and region of interest parameters
    -  include some caching to smooth changes .
    -  add color filter to add another way to detect the lanes.
    
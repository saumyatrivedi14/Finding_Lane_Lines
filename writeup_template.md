# **Finding Lane Lines on the Road** 


The goals of this project are the following:
* Make a pipeline that finds lane lines on the statetic images of road
* Incorporate the same pipeline in videos.

[//]: # (Image References)

[image1]: ./test_images_output/Original.JPG "Raw Image"
[image2]: ./test_images_output/yellow_filter.jpg "Yellow Filter"
[image3]: ./test_images_output/white_filter.jpg "White Filter"
[image4]: ./test_images_output/combined_Image.PNG "Combined Yellow and White Filters"
[image5]: ./test_images_output/gaussian_gray.jpg "Gaussian Gray"
[image6]: ./test_images_output/canny_edge.jpg "Canny Edge Detection"
[image7]: ./test_images_output/masking_roi.JPG "Region of Interest"
[image8]: ./test_images_output/hough_lines.PNG "Hough Lines"
[image9]: ./test_images_output/final_image.jpg "Final Lines"

---

### Reflection

### 1. Pipeline Steps Explained

* First it takes the raw image as shown below.

![alt text][image1]

* Using RGB to HSL color space conversion, Yellow shades are filtered out as shown in figure below.

![alt text][image2]

* Same way, filter out the white lanes in an image.

![alt text][image3]

* Combining both these images, will give both yellow and white lanes in an image.

![alt text][image4]

* The combined image is then converted to grayscale and Gaussian smoothing of kernel size 9 is applied and the output is shown below.

![alt text][image5]

* Canny Edge Detection is used to find the edges from the grayscaled image as shown in the figure below.

![alt text][image6]

* Region of interest is filtered out by using the build in functions.

![alt text][image7]

* Hough's Lines are ofund using the cv2.HoughLinesP() function given in build in functions.

![alt text][image8]

* Finally those lines are expolated and using statistical tools, final two lane lines are found.

![alt text][image9]


### 2. Identify potential shortcomings with your current pipeline

There are three shortcomings of the current pipeline, first, in the challenge video, It does not find the find lanes under shadows because that particular gradient is not being incorporated in the white filter which is being applied initially. Second, The lines do not remain smooth between each frames in the video, I tried standard deviation technique and also thought of moving average but still the output is not smooth enough. Third, It does not account the curves on the road, which I think will be done in the Advance Lane Finding Project in coming weeks.

### 3. Suggest possible improvements to your pipeline

A possible improvements are to implement an algorithm which takes in different gradients of yellow and white (under shadows) intelligently and keeps curved lane lines for curve roads.

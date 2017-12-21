# **Finding Lane Lines on the Road** 


The goals of this project are the following:
* Make a pipeline that finds lane lines on the statetic images of road
* Incorporate the same pipeline in videos.

[//]: # (Image References)

[image1]: ./test_images_output/Pipeline/Original.JPG "Raw Image"
[image2]: ./test_images_output/Pipeline/yellow_filter.jpg "Yellow Filter"
[image3]: ./test_images_output/Pipeline/white_filter.jpg "White Filter"
[image4]: ./test_images_output/Pipeline/combined_Image.PNG "Combined Yellow and White Filters"
[image5]: ./test_images_output/Pipeline/gaussian_gray.jpg "Gaussian Gray"
[image6]: ./test_images_output/Pipeline/canny_edge.jpg "Canny Edge Detection"
[image7]: ./test_images_output/Pipeline/masking_roi.JPG "Region of Interest"
[image8]: ./test_images_output/Pipeline/hough_lines.PNG "Hough Lines"
[image9]: ./test_images_output/Pipeline/final_image.jpg "Final Lines"
[image10]: ./test_images_output/solidWhiteCurve.JPG "solidWhiteCurve"
[image11]: ./test_images_output/solidWhiteRight.JPG "solidWhiteRight"
[image12]: ./test_images_output/solidYellowCurve.JPG "solidYellowCurve"
[image13]: ./test_images_output/solidYellowCurve2.JPG "solidYellowCurve2"
[image14]: ./test_images_output/solidYellowLeft.JPG "solidYellowLeft"
[image15]: ./test_images_output/whiteCarLaneSwitch.JPG "whiteCarLaneSwitch"


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

There are three shortcomings of the current pipeline, first, in the challenge video, It does not find the find lanes under shadows and on brigde because some further calibration of parameters is required and also the gradient range of yellow and white filter needs to be improved. Second, The lines do not remain smooth between each frames in the video, I tried standard deviation technique and also thought of moving average but still the output is not smooth enough. Third, It does not account the curves on the road, which I think will be taught in the Advance Lane Finding Project in coming weeks.

### 3. Suggest possible improvements to your pipeline

A possible improvements are to implement an algorithm which takes in different gradients of yellow and white (under shadows or over brigde) intelligently and keeps curved lane lines for curve roads.

### 4. Output of Test Images

![alt text][image10]
![alt text][image11]
![alt text][image12]
![alt text][image13]
![alt text][image14]
![alt text][image15]


# **Finding Lane Lines on the Road** 


The goals of this project are the following:
* Make a pipeline that finds lane lines on the statetic images of road
* Incorporate the same pipeline in videos.

[//]: # (Image References)

[image1]: ./test_images_output/Original.JPG "Raw Image"
[image2]: ./test_images_output/yellow_filter.JPG "Yellow Filter"
[image3]: ./test_images_output/white_filter.JPG "White Filter"
[image4]: ./test_images_output/combined_Image.PNG "Combined Yellow and White Filters"
[image5]: ./test_images_output/gaussian_gray.JPG "Gaussian Gray"
[image6]: ./test_images_output/canny_edge.JPG "Canny Edge Detection"
[image7]: ./test_images_output/masking_roi.JPG "Region of Interest"
[image8]: ./test_images_output/hough_lines.PNG "Hough Lines"
[image9]: ./test_images_output/final_image.JPG "Final Lines"

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


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...

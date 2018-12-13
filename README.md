# **Finding Lane Lines on the Road** 

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on the work

---

### Reflection

### The pipeline consists of 6 steps. 

1. The first step is to convert images to grayscale.
2. The grayscale images are blurred using gaussian smoothing.
3. The blurred images are fed to canny algorithm to identify edges.
4. The images with edges are masked with a filtered region relevant to the lane lines
5. These masked edges are transformed into hough space using hough transform to identify signicant edges such as lane lines.
6. In order to draw a single line on the left and right lanes, the draw_lines() function finds lines with maximum and minimum slope respectively. The masked edges within the vicinity of these left and right lane lines are averaged to arrive at generic lane lines for the given data.

The pipeline is simple to build and most of the time in the project is spent to tune the parameters and suit the model for the given data. 


### 2. Potential shortcomings with current pipeline
1. The tuning is done by averaging out lane lines from several images and average may not be the best method always.
2. In darkness or low light, it may be difficult to extract lane lines as above with the same accuracy.
3. Straight lines are fit to find lane lines but in reality, lane lines can be curvy in nature near turns. The model may not consider such scenarios.


### 3. Possible improvements to pipeline in future
1. There can be better ways of obtaining generic lane lines with methods such as weighted average. We can use a cost function to determine the best method.
2. We may require better image processing techniques to handle scenarios such as low light or darkness.
2. We could use quadratic and higher order curves to find lane lines near turns.

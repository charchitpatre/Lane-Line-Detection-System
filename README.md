# Lane-Line-Detection-System
In this project, I have used Python and OpenCV to detect lane-line on the roads. It works on the series of processing steps which works on a series of individual images, at the end giving an output in the form of a video.


Step by Step architecture:
1. Loading camera images.
2. Applying Color Selection
3. Applying Canny Edge Detection.
   3.1 Applying Gray Scaling to the images.
   3.2 Applying Gaussian Smoothing.
   3.3 Performing Canny Edge Detection.
4. Determining the Region of Interest.
5. Applying Hough Transform.
6. Average and Extrapolating the lane lines.
7. Applying on video clip.

Software Required:-
1. Anaconda
2. Python
3. OpenCV

Hardware Requirement:-
1. HD Camera

Our goal is to create a program that can read a video stream and output an annotated video that shows the following:
1. The current lane
2. The radius of curvature of the lane
3. The position of the vehicle relative to the middle of the lane

Methodology

1. Capturing and decoding video file: 
        We will capture the video using Video Capture object and after the capturing has been initialized every video frame is decoded (i.e. converted into a sequence of images).

2. Grayscale conversion of image: 
        The video frames are in RGB format, RGB is converted to grayscale because processing a single channel image is faster than processing a three-channel colored image.

3. Reduce noise: 
        Noise can create false edges, therefore before going further, it’s imperative to perform image smoothening. Gaussian filter is used to perform this process.

4. Canny Edge Detector: 
        It computes gradient in all directions of our blurred image and traces the edges with large changes in intensity.

5. Region of Interest: 
        This step is to take into account only the region covered by the road lane. A mask is created here, which is of the same dimension as our road image. Furthermore, bitwise AND operation is performed between each pixel of our canny image and this mask. It ultimately masks the canny image and shows the region of interest traced by the polygonal contour of the mask.

6. Hough Line Transform: 
        The Hough Line Transform is a transform used to detect straight lines. The Probabilistic Hough Line Transform is used here, which gives output as the extremes of the detected lines.


![image](https://user-images.githubusercontent.com/70278613/180045900-b609e041-2450-4ae8-bbaf-f6b735060c22.png)

Self Driving Car is one of AI’s most innovative technologies. Self Driving Cars use lane-Line detection OpenCV features to detect lane of the roads and they are trained not to drive outside of the lane.

However, there are going to be many scenarios where this solution will not work. For example, when there will be no lane markings, or when there is too much of traffic on the road, or detecting curved lane-line is behind the scope of this, the system will fail. There are more sophisticated methods to overcome such problems in lane-line detection.  This project is intended to only detect (mostly) straight lines. 

Advantages
1. This system ensures vehicle don’t move out of their lanes.
2. Constant Speed and Efficient drive

Disadvantages
1. Requires active internet connection.
2. Time to time updates.



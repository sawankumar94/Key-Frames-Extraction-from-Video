# Key-Frame-Extraction-from-Videos
Using Color Histogram, SVD and Dynamic Clustering Method obtained Key-Frames from a video. 

The color histogram for each of the 3*3 blocks i.e 9 blocks/parts of frames in the video are generated in all three channels (RGB) of 6 bins each. These nine histograms are then concatenated together to form a 1944-dimensional feature vector for the frame.
The dimension of this multidimensional array is (1832, 1944). There are 1832 frames.
I performed dimension reduction using SVD. The top 63 singular values were from 76082 to 508.  So, new reduced dimension is (1832, 63). Then, I created clusters of consecutive frames (similar frames) by using Cosine Similarity to check whether the new frame is similar to the last cluster formed or not. This method is called Dynamic Clustering. The frames in the sparse clusters are considered as transition between shots, so they are ignored. The frames in a dense cluster make a shot, so i chose its last element as a key-frame. 

The code is well documented.

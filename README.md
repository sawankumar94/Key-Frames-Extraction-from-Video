# Key-Frame-Extraction-from-Videos
Using Color Histogram, SVD and Dynamic Clustering Method obtained Key-Frames from a video. 

The color histogram for each of the frames in the video are generated in all three channels (RGB) of 16 bins each. Then color histogram from all channels flattened to large dimension i.e 4096 for each of the frames to obtain multidimensional array where rows represents frames and columns represents features for each frame. The dimension of this multidimensional array is (1832, 4096). There are 1832 frames.
I performed dimension reduction using SVD. The top 15 singular values were from 44152 to 2045.  So, new reduced dimension is (1832, 15). Then, I created clusters of consecutive frames (similar frames) by using Cosine Similarity to check whether the new frame is similar to the last cluster formed or not. This method is called Dynamic Clustering. The frames in the sparse clusters are considered as transition between shots, so they are ignored. The frames in a dense cluster make a shot, so i chose its last element as a key-frame. 

The code is well documented.

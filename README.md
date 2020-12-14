# Key-Frames-Extraction-from-Video

Project: Key-Frames Extraction from Video

Definition & Main Idea: Key-frame refers to the image frame in the video that represents and summarizes it. These can be selected as shot boundaries if we can detect shots and ignore transitions between them.

Summary: Used Color Histogram, SVD and Dynamic Clustering Method to obtain Key-Frames from a video.

The color histogram for each of the 3*3 blocks i.e. 9 blocks of frames in the video are generated in all three channels (RGB) of 6 bins each. The nine histograms were then concatenated to form a 1944-dimensional feature vector for every frame to create a feature-frame matrix of dimension (1832, 1944) for the entire video. There were total 1832 frames. I performed dimension reduction on matrix using SVD, then the new reduced dimension was (1832, 63). Then, I created clusters of consecutive frames by using Cosine Similarity to check whether the new frame was similar to the last cluster formed or not. This method is called Dynamic Clustering. The frames in the sparse clusters are considered as transition between shots, so they were ignored. The frames in a dense cluster make a shot and I chose shots’ last added frame as a key-frame.


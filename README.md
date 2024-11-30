# Introduction
This project analyzes video data to detect faces, extract facial embeddings using the DeepFace library, and then clusters the faces using DBSCAN. The goal is to group similar faces together, eliminate duplicates, and generate a report that includes performance metrics for each cluster along with the dominant emotion for each representative face.


# Files:
Assignment Data.xlsx: Excel file containing video URLs and performance metrics. The Video URL column should contain the path to the video file, and the Performance column should contain a numeric value representing the performance metric associated with each video.

Output.docx: The generated Word document that contains the cluster analysis, including the representative face image for each cluster, average performance, and dominant emotion.


# How It Works:
## Face Detection:
The script uses dlib to detect faces in frames of the videos. It processes each video and extracts frames at regular intervals (50 frames by default).

## Face Embeddings:
For each detected face, DeepFace is used to extract facial embeddings, which are numerical representations of the face. These embeddings capture unique features of the face, such as geometry and expression.

## Clustering with DBSCAN:
DBSCAN (Density-Based Spatial Clustering of Applications with Noise) is used to cluster the face embeddings. It groups similar faces together and labels outliers (faces that do not fit into any cluster) with -1.

## Duplicate Removal:
Duplicate faces within the same cluster are removed by comparing their embeddings using cosine similarity. If two faces are similar (based on a cosine similarity threshold of 0.95), one is discarded.

## Emotion Analysis:
DeepFace's emotion analysis is used to determine the dominant emotion (e.g., happy, sad, angry) for each representative face.

## Report Generation:
The script generates a Word document that contains a table with cluster statistics, including the average performance score, representative face image, and dominant emotion for each cluster.


# Notes:
The cosine similarity threshold (0.95) used for eliminating duplicates can be adjusted based on how strict or lenient you want the duplicate detection to be.
The DBSCAN parameters (eps and min_samples) can also be adjusted for different clustering behavior depending on the density of your data.


# Example Output (Word Document):
Cluster 0:
Average Performance: 1.0
Face Image:
Dominant Emotion: Happy

Cluster 1:
Average Performance: 1.5
Face Image:
Dominant Emotion: Neutral

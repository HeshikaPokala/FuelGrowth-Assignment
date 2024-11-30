# Introduction
This project analyzes video data to detect faces, extract facial embeddings using the DeepFace library, and then clusters the faces using DBSCAN. The goal is to group similar faces together, eliminate duplicates, and generate a report that includes performance metrics for each cluster along with the dominant emotion for each representative face.

# Features
## Face Detection: 
Detect faces in video frames using the dlib detector.
Face Embeddings: Extract facial embeddings using the DeepFace library.
Clustering: Use DBSCAN for clustering faces based on their embeddings.
Duplicate Removal: Remove duplicate faces within clusters by comparing embeddings using cosine similarity.
Emotion Analysis: Identify the dominant emotion for each representative face.
Report Generation: Create a Word document report with clusters, performance stats, and emotion analysis.

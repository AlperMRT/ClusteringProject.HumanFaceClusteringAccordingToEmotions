Internship Project

Project Due Date: 23.09.2024

Dataset used: [https://www.kaggle.com/datasets/noamsegal/affectnet-training-data](url)

This project aims to cluster human face images according to their emotions. The dataset contains a total of 500 images, 100 images from 5 emotions. By using different feature extraction methods and clustering methods, I tried to see which combination is better for such this case.

As feature extraction methods, I chose HOG, LBP, VGGNET, RESNET and Geometric Feature Extraction using Landmark. For geometric features, I downloaded "shape_predictor_68_face_landmarks.dat". Then with 3 main process to get geometric feature vector: Converting image RGB to YCbCr, mask operation, segmentation.

As clustering methods, I chose K-Means, DBSCAN and Deep Embedded Clustering (DEC). 

In testing, first I tried every feature vectors with all 3 clustering methods one by one. The Silhouette Score results are below:

K-means	DBSCAN	DEC

Geometric Vector	0.91	0.97	0.91

LBP Vector	0.45	0.25	0.46

HOG Vector	0.03	0.06	0.01

VGGNET Vector	0.07	0.35	0.04

RESNET Vector	0.07	0.34	0.05

Then I combined all feature vectors with geometric vector one by one, since it has the highest Silhouette Scores with all clustering methods. The combined feature vectors' results are below:

K-means	DBSCAN	DEC

Geometric-LBP	0.91	0.97	0.91

Geometric-HOG	0.09	0.07	0.08

Geometric-VGGNET	0.10	0.33	0.10

Geometric-RESNET	0.10	0.33	0.14

As seen from the tables, geometric feature vector is the best feature vector for single usage. For combined vectors, the combination of geometric feature vector and LBP feature vector gives the best result. When we compare all the scores for the clustering algorithms, we see that DBSCAN generally produces the best scores.



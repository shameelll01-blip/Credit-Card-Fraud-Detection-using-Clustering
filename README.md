# Credit-Card-Fraud-Detection-using-Clustering
Credit Card Fraud Detection using Clustering (K-Means)
Project Overview
This project focuses on detecting fraudulent credit card transactions using unsupervised learning (clustering) techniques. Since fraud cases are extremely rare, this is treated as an anomaly detection problem rather than a traditional classification task.

Objective
Apply K-Means clustering to identify unusual (fraudulent) transactions
Detect anomalies based on distance from cluster centroids
Evaluate how well detected anomalies match actual fraud cases
Dataset
Source: Kaggle - Credit Card Fraud Detection Dataset

Contains anonymized transaction features (V1–V28), Time, Amount, and Class

Class:

0 → Normal transaction
1 → Fraud transaction
The dataset is highly imbalanced (fraud ≈ 0.17%).

Methodology
1. Data Understanding
Loaded dataset using Pandas
Checked shape, columns, and missing values
Analyzed class distribution
Fraud detection is treated as anomaly detection because fraudulent transactions are rare and differ from normal patterns.

2. Data Preprocessing
Removed Class column for unsupervised learning
Applied StandardScaler for feature scaling
3. Clustering (K-Means)
Used Elbow Method to determine optimal number of clusters (K)
Trained K-Means model
Assigned cluster labels to each transaction
4. Anomaly Detection
Computed distance from each point to nearest centroid
Selected top 1% farthest points as anomalies
Labeling:

1 → Anomaly (Predicted Fraud)
0 → Normal
5. Evaluation
Compared predicted anomalies with actual labels using:

Confusion Matrix
Precision
Recall
Key metrics:

Precision: Accuracy of detected frauds
Recall: Ability to detect actual frauds
In fraud detection, recall is more important because missing fraud is costly.

6. Visualization
Applied PCA (Principal Component Analysis) to reduce data to 2D
Visualized clusters and anomalies vs normal transactions
Results
K-Means grouped similar transactions effectively
Distance-based method identified potential fraud cases
Performance depends on choice of K and anomaly threshold
Technologies Used
Python
Pandas
NumPy
Scikit-learn
Matplotlib
How to Run
Download dataset from Kaggle
Place creditcard.csv in your project folder
Run the script:
python fraud_detection.py
Or use Jupyter Notebook:

jupyter notebook
Key Insights
Fraud detection is difficult due to extreme class imbalance
Unsupervised learning helps detect unknown fraud patterns
Distance from centroid is a simple and effective anomaly measure
Future Improvements
Use DBSCAN for better anomaly detection
Try Isolation Forest or Autoencoders
Tune anomaly threshold dynamically
Apply advanced imbalance handling techniques
Conclusion
This project demonstrates how clustering can be used to detect fraudulent transactions without labeled training data. K-Means provides a simple baseline, while more advanced models can further improve performance.

Acknowledgment
Dataset provided by the Kaggle community.

<img width="1203" height="663" alt="image" src="https://github.com/user-attachments/assets/f98b40f4-e673-4a51-9e6d-a6a17dba1bef" /># Machine Learning and Pattern Recognition — Lab 5

Face Detection, Clustering and Classification using OpenCV + KMeans

---

## Objective

The objective of this experiment is to perform automatic face detection from an image, group similar faces using unsupervised learning, and classify a new face into one of the learned groups.

The experiment demonstrates the complete pipeline:
**Detection → Feature Extraction → Clustering → Classification**

---

## Step 1: Face Detection

The input image `Plaksha_Faculty.jpg` is processed using the Haar Cascade frontal face classifier provided by OpenCV.

### Procedure

1. Read image using OpenCV
2. Convert to grayscale
3. Apply Haar Cascade classifier
4. Draw bounding boxes around detected faces
5. Display total number of faces detected

### Method Used

Haar Cascade detects faces based on contrast patterns such as:

* Eye region darker than cheeks
* Nose bridge brightness
* Facial symmetry

### Output

All faces in the faculty image were successfully detected and labeled.

---

## Step 2: Feature Extraction (HSV Color Space)

Each detected face is converted from **BGR → HSV color space**.

From each face we compute:

* Mean Hue (H)
* Mean Saturation (S)

These values represent skin tone characteristics and are used as features.

Thus each face becomes a 2-D feature vector:

Feature Vector = (Hue, Saturation)

---

## Step 3: Face Clustering using K-Means

We cluster faces into groups based on similarity of color characteristics.

### Algorithm

K-Means Clustering (k = 2)

The algorithm:

1. Chooses 2 random centroids
2. Assigns each face to nearest centroid
3. Updates centroid positions
4. Repeats until stable

### Visualization

Each face is plotted on a Hue vs Saturation graph.

* Green points → Cluster 0
* Blue points → Cluster 1
* Red X → Cluster Centroids

This groups visually similar faces together.

---

## Step 4: Face Classification

A new face image `Dr_Shasi_Tharoor.jpg` is introduced.

Steps:

1. Detect face
2. Extract Hue & Saturation
3. Use trained KMeans model
4. Predict cluster membership

The new face is plotted on the same graph to determine which group it belongs to.

---

## Observations

* Faces with similar skin tone cluster together
* KMeans successfully separated the dataset into distinct groups
* The template face was assigned to the nearest centroid cluster
* HSV features are effective for grouping faces without labels

---

## Conclusion

This experiment demonstrates an end-to-end unsupervised learning pipeline:

Face Detection → Feature Engineering → Clustering → Classification

Haar Cascade provides reliable face localization, while KMeans groups faces using color distribution without requiring training labels.

The system successfully classifies a new unseen face into an existing group, proving the effectiveness of feature-based clustering for pattern recognition.

---

## Technologies Used

* Python
* OpenCV
* NumPy
* Matplotlib
* Scikit-learn (KMeans)
---

## Output Visualizations
1.Face Clusters based on hue and saturation
<img width="1199" height="642" alt="kmeans_clustering" src="https://github.com/user-attachments/assets/12fe780e-c054-49b8-9b9d-b87ba671c227" />
2. Clustered faces with centroids
<img width="1214" height="655" alt="kmeans_face_clustering" src="https://github.com/user-attachments/assets/a6906319-f14d-45e7-86c5-a153b48b425c" />
3. Template Image Classification
<img width="1203" height="663" alt="template_" src="https://github.com/user-attachments/assets/0724bd83-6e00-406b-a75c-bd5285f35d96" />
4.Final Clustering with Template Image
<img width="1282" height="672" alt="image" src="https://github.com/user-attachments/assets/8bb3dff2-fade-45f5-9d93-48834d088deb" />







---

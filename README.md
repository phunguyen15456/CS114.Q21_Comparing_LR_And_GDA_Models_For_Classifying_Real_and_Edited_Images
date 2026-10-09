#  Machine Learning Final Project (CS114)

**TOPIC: A COMPARISON OF LOGISTIC REGRESSION AND GAUSSIAN DISCRIMINANT ANALYSIS FOR REAL AND MANIPULATED IMAGE CLASSIFICATION**

*University of Information Technology - VNU-HCM (UIT)*

*Class Code:* CS114.Q21

## Instructor

**Dr. Vo Nguyen Le Duy**

##  Team Members (Group 11)

| No. | Full Name | Student ID | 
| ----- | ----- | ----- | 
| 1 | Ly Hoai Phong | 24521334 | 
| 2 | Le Minh Phu | 24521354 | 
| 3 | Nguyen Binh Phu | 24521356 | 
| 4 | Tang Nguyen Bao Quynh | 24521512 | 
| 5 | Nguyen Tran Tai | 24521556 | 
| 6 | Bui Trong Tan | 24521573 | 

## Project Summary

The rapid development of image editing tools makes distinguishing authentic images from manipulated ones a significant challenge in computer vision and machine learning. This project aims to compare the performance of two traditional machine learning models in classifying real images and edited/manipulated (fake) images.

### 1. Dataset

The project utilizes the **Real & Fake Images Dataset For Image Forensics** (by Shivam Ardeshna), which consists of a balanced distribution of real and fake images divided into 3 sets:

* **Train:** 40,002 images
* **Test:** 12,360 images
* **Validation:** 5,227 images

### 2. Preprocessing & Feature Extraction

Input images ($128\times128\times3$) are processed using advanced feature extraction techniques to detect manipulation traces:

* **ELA (Error Level Analysis):** Detects anomalies via JPEG compression errors.
* **FFT (Fast Fourier Transform):** Analyzes images in the frequency domain, especially in high-frequency bands.
* **LBP (Local Binary Pattern):** Extracts structural texture features.
* **YCbCr Color Space:** Exploits micro-color errors on the Cb and Cr channels.

The data is then normalized using *Standard Scaler* and reduced in dimensionality using *PCA* (retaining approximately 700 principal components) to optimize training.

### 3. Models & Methodology

We trained and compared two algorithms:

1. **Logistic Regression** (Linear classification model)
2. **Gaussian Discriminant Analysis - GDA** (Generative classification model)

Evaluation metrics include Accuracy, Precision, Recall, $F_1$-score, and ROC-AUC.

### 4. Key Findings

Both models achieved decent classification performance and prioritized fake image detection (maintaining a low False Negative rate):

* **GDA** yielded a slightly higher Accuracy on the test set (71.19% compared to 70.9% for Logistic Regression) due to its ability to model multidimensional data distribution structures.
* **Logistic Regression** demonstrated higher stability in class separation, achieving a better ROC-AUC score (0.8079 compared to 0.8055).
* **Overall Conclusion:** Both models have comparable capabilities. However, the task remains challenging due to the significant overlap between the two classes. Future improvements could involve applying Deep Learning architectures (CNNs, Vision Transformers) or expanding the dataset to include modern AI-generated forgeries (GANs, Diffusion Models).

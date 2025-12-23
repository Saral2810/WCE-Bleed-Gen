DMP-WCEBleedNet: Automated Bleeding Detection in WCEDual-Branch Deep Learning Architecture for Segmentation and Classification of Wireless Capsule Endoscopy Images.

📌 Overview
This project focuses on the automated detection and localization of gastrointestinal bleeding using Wireless Capsule Endoscopy (WCE) images. Identifying bleeding manually is a time-consuming task for clinicians due to the thousands of frames generated per scan.DMP-WCEBleedNet leverages a dual-task learning approach to simultaneously perform:Binary Classification: Distinguishing between "Bleeding" and "Non-Bleeding" frames.
Semantic Segmentation: Generating precise pixel-level masks to pinpoint the bleeding regions.

🏗️ Architecture
The core of this repository is the Dual-Mode/Multi-Path (DMP) architecture. It utilizes a ResNet-based UNet backbone to extract high-level features while maintaining spatial resolution for accurate mask generation.
Key Components:Encoder: Pre-trained ResNet backbone for robust feature extraction.
Decoder: Symmetrical expanding path with skip connections to recover spatial details.
Dual Head:Segmentation Head: Sigmoid activation producing a 2D probability map.
Classification Head: Global Average Pooling followed by fully connected layers to predict the class.

📊 Dataset
The model is trained and evaluated on the WCEBleedGen dataset.
Input: 3-channel RGB images from capsule endoscopy.
Ground Truth: Corresponding binary masks where white pixels ($255$) represent bleeding zones.

🚀 Key Features
Hybrid Loss Function: Combines Binary Cross-Entropy (BCE) with Dice Loss to handle class imbalance in medical masks.
Advanced Augmentation: Utilizes the albumentations library (Horizontal/Vertical flips, Random Rotations, and Color Jitter) to improve model generalization.
Performance Metrics:Segmentation: Dice Coefficient, Mean Intersection over Union (mIoU).Classification: Accuracy, Precision, Recall, and ROC-AUC.

📈 Results
The model achieves high sensitivity in detecting even small hemorrhagic areas.
Accuracy, Precision, Recall, F1-Score
Dice Coefficient for segmentation
ROC-AUC curves
Confusion matrices for both tasks

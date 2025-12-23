WCEBleedGen: Dual-Task Deep Learning System for Bleeding Detection and Segmentation

Wireless Capsule Endoscopy (WCE) generates thousands of gastrointestinal images per patient, making manual bleeding detection time-consuming and error-prone. This project presents a dual-task deep learning framework that simultaneously performs bleeding classification and pixel-level bleeding segmentation from WCE images.

The system is designed to assist clinicians by providing both a binary bleeding decision and an interpretable segmentation mask highlighting bleeding regions.

Key Features

• Dual-task architecture combining classification and segmentation
• ResNet-based encoder with UNet-style decoder
• End-to-end training with joint loss optimization
• Robust data augmentation for medical image variability
• Detailed evaluation using Dice, ROC-AUC, precision, recall, F1, and confusion matrices

Model Architecture

The proposed DMP_WCEBleedNet consists of:

A shared encoder for feature extraction

A classification head producing bleeding logits

A segmentation decoder generating pixel-wise masks

Loss Function:

BCEWithLogitsLoss for classification

Dice Loss / BCE for segmentation

Combined multi-task loss for joint optimization

Architecture and training flow are illustrated in the docs/ folder.

Workflow Overview

Load raw WCE images and corresponding masks

Apply preprocessing and data augmentation

Split dataset into train, validation, and test sets

Train the dual-task model using Adam optimizer

Validate using thresholded segmentation outputs

Evaluate performance using classification and segmentation metrics

Visualize results and export metrics

Results & Evaluation

The system evaluates:

Accuracy, Precision, Recall, F1-Score

Dice Coefficient for segmentation

ROC-AUC curves

Confusion matrices for both tasks

All metrics, plots, and logs are saved for reproducibility.

Tech Stack

Python

PyTorch

Torchvision

NumPy, Pandas

OpenCV

Matplotlib, Seaborn

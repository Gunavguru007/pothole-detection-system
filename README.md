Pothole Detection System

A robust computer vision project for automatically detecting and localizing potholes in images using the YOLO (You Only Look Once) object detection model. This system is designed to aid in road maintenance and infrastructure monitoring.

https://P_curve.png
📋 Project Overview

This project implements a complete machine learning pipeline for pothole detection, including data preparation, model training, evaluation, and results analysis. The trained model achieves high precision in identifying potholes, making it suitable for real-world applications.
✨ Key Features

    High-Performance Detection: Achieved 1.00 precision at 0.874 confidence threshold

    YOLO Architecture: Utilizes state-of-the-art object detection capabilities

    Comprehensive Evaluation: Detailed analysis using precision-recall curves, confusion matrices, and F1 scores

    Custom Dataset: Trained and validated on a diverse set of pothole images

📊 Performance Metrics

    Precision: 1.00 at confidence threshold 0.874

    mAP50: Detailed metrics available in evaluation results

    F1-Score: Comprehensive F1-Confidence curve analysis

    Confusion Matrix: Normalized and standard matrices for model assessment

🛠️ Installation
Prerequisites

    Python 3.8+

    PyTorch 1.7+

    OpenCV

    Ultralytics YOLO

Setup
bash

# Clone the repository
git clone https://github.com/Gunavguru007/pothole-detection-system.git
cd pothole-detection-system

# Install dependencies
pip install -r requirements.txt

🚀 Usage
Training
python

from ultralytics import YOLO

# Load model
model = YOLO('yolov8n.pt')  # or your custom configuration

# Train the model
results = model.train(
    data='pothole_dataset.yaml',
    epochs=100,
    imgsz=640,
    batch=16
)

Inference
python

# Run detection on an image
results = model('path/to/your/image.jpg')

# Display results
results[0].show()

📁 Project Structure
text

pothole-detection-system/
├── datasets/
│   ├── train/
│   ├── val/
│   └── test/
├── models/
│   ├── best.pt
│   └── last.pt
├── results/
│   ├── confusion_matrix.png
│   ├── P_curve.png
│   ├── F1_curve.png
│   └── results.png
├── training/
│   └── training_scripts/
├── requirements.txt
└── README.md

📈 Results
Training Progress

https://results.png
Confusion Matrix

https://confusion_matrix.png
F1-Confidence Curve

https://F1_curve.png

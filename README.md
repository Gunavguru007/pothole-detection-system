Pothole Detection System

A robust computer vision system for automatic pothole detection and localization using YOLO (You Only Look Once) object detection.
📋 Project Overview

This project implements a complete machine learning pipeline for detecting potholes in images. The system achieves high precision in identifying road defects, making it suitable for infrastructure maintenance, road safety applications, and autonomous vehicle navigation.
🚀 Features

    High Precision Detection: Achieved 1.00 precision at 0.874 confidence threshold

    Real-time Capable: YOLO architecture enables fast inference

    Comprehensive Evaluation: Detailed metrics including F1-score, mAP50, and confusion matrices

    Custom Dataset: Trained on diverse pothole images under various conditions

📊 Performance Metrics
Key Results

    Precision: 1.00 at confidence threshold 0.874

    Recall: Comprehensive evaluation completed

    mAP50: Detailed metrics available in results

    F1-Score: Optimized confidence-performance balance

Model Performance
<img width="2250" height="1500" alt="F1_curve" src="https://github.com/user-attachments/assets/ab8eb89d-40c7-483f-9560-410a84cb397e" />
<img width="2250" height="1500" alt="PR_curve" src="https://github.com/user-attachments/assets/fdd30b7c-f750-4f5c-8a64-a9723aa6f088" />
<img width="2250" height="1500" alt="R_curve" src="https://github.com/user-attachments/assets/3ce724ba-73b2-4cc1-be3e-5956f7eac68d" />
<img width="2250" height="1500" alt="P_curve" src="https://github.com/user-attachments/assets/bc6f7090-6aab-4737-bcce-01c9df6a34b6" />

🛠️ Installation
Prerequisites

    Python 3.8+

    PyTorch 1.7+

    OpenCV

    Ultralytics YOLO

Setup
bash

# Clone repository
git clone https://github.com/Gunavguru007/pothole-detection-system.git
cd pothole-detection-system

# Install dependencies
pip install -r requirements.txt

Requirements
txt

torch>=1.7.0
torchvision>=0.8.0
ultralytics>=8.0.0
opencv-python>=4.5.0
numpy>=1.19.0
matplotlib>=3.3.0
pillow>=8.0.0

🏃‍♂️ Usage
Training
python

from ultralytics import YOLO

# Load model
model = YOLO('yolov8n.pt')  # or custom architecture

# Train the model
results = model.train(
    data='pothole_dataset.yaml',
    epochs=100,
    imgsz=640,
    batch=16
)

Inference
python

# Detect potholes in images
results = model('path/to/image.jpg')

# Display results
results[0].show()

# Save results
results[0].save('output.jpg')

Evaluation
python

# Validate model performance
metrics = model.val()
print(f"mAP50-95: {metrics.box.map}")
print(f"mAP50: {metrics.box.map50}")

📁 Project Structure
text

pothole-detection-system/
├── datasets/
│   ├── images/          # Training and validation images
│   └── labels/          # Annotation files
├── models/              # Trained model weights
├── utils/               # Utility scripts
├── results/             # Training results and metrics
├── requirements.txt     # Python dependencies
├── train.py            # Training script
├── detect.py           # Inference script
└── README.md           # Project documentation

📈 Model Architecture

This project utilizes the YOLO (You Only Look Once) architecture for real-time object detection. The model was trained on a custom dataset of pothole images with comprehensive data augmentation techniques.
Training Details

    Architecture: YOLOv8

    Input Size: 640x640 pixels

    Augmentation: Mosaic, HSV, Flip, Scale

    Optimizer: AdamW

    Loss Function: Complete YOLO loss (box, cls, dfl)

🗂️ Dataset

The model was trained on a proprietary dataset containing:

    1000+ annotated pothole images

    Various lighting conditions

    Different road types and surfaces

    Multiple pothole sizes and shapes

Dataset Statistics
![labels_correlogram](https://github.com/user-attachments/assets/425b0efb-c3a2-4043-a775-410709d0121e)
![labels](https://github.com/user-attachments/assets/f4d2c3f4-f642-4794-a2e0-ba3efbb06f18)

📊 Evaluation Results
Confusion Matrix
<img width="3000" height="2250" alt="confusion_matrix_normalized" src="https://github.com/user-attachments/assets/43f9a7d2-63c1-4f74-8c3e-e75a41214823" />
<img width="3000" height="2250" alt="confusion_matrix" src="https://github.com/user-attachments/assets/af5ef491-baf6-4b4d-affb-6e6e1a885fbf" />

Training Progress

    Box Loss: Consistent decrease indicating better localization

    Classification Loss: Stable improvement in class prediction

    Precision/Recall: Balanced improvement throughout training

Sample Detections
![val_batch2_pred](https://github.com/user-attachments/assets/6242b004-4e4e-49c4-98d8-d05e1699627d)
![val_batch0_labels](https://github.com/user-attachments/assets/f45cc5de-dedd-420b-9955-3897ba91dffc)
![val_batch0_pred](https://github.com/user-attachments/assets/90658ec5-5cf8-4d91-99da-ec49aab01d6c)
![val_batch1_labels](https://github.com/user-attachments/assets/fefe0605-8a38-4aa2-9402-74d149767f13)
![val_batch1_pred](https://github.com/user-attachments/assets/f88e5672-e1c5-46ba-848b-a061fba5bb0b)
![val_batch2_labels](https://github.com/user-attachments/assets/bb34ed8e-c90b-4751-8653-be0130023b1d)
![train_batch1](https://github.com/user-attachments/assets/92215d4f-a394-441e-9775-6136c314c0e0)
![train_batch0](https://github.com/user-attachments/assets/cac469ef-465c-4932-aa71-0f64be58809f)
![train_batch2](https://github.com/user-attachments/assets/eac3451e-4d8b-4b7d-8ea5-b25549e2af22)
![train_batch18361](https://github.com/user-attachments/assets/aaf6b706-7db9-42bf-b315-1726c114d467)
![train_batch18360](https://github.com/user-attachments/assets/b5d78af8-d499-44a0-bfdf-a3ee51681665)
![train_batch18362](https://github.com/user-attachments/assets/f13b4d7e-7632-4fae-81ad-42f1c354896c)
<img width="2400" height="1200" alt="results" src="https://github.com/user-attachments/assets/5337e822-59a7-4f0f-9e60-26f58df5cd52" />

🎯 Applications

    Road Maintenance: Automated pothole detection for municipal authorities

    Autonomous Vehicles: Enhanced perception for self-driving cars

    Insurance Claims: Objective evidence for road damage claims

    Infrastructure Planning: Data-driven decision making for road repairs

🤝 Contributing

We welcome contributions! Please feel free to submit pull requests, report bugs, and suggest new features.

    Fork the repository

    Create your feature branch (git checkout -b feature/AmazingFeature)

    Commit your changes (git commit -m 'Add some AmazingFeature')

    Push to the branch (git push origin feature/AmazingFeature)

    Open a Pull Request

📄 License

This project is licensed under the MIT License - see the LICENSE file for details.
🙏 Acknowledgments

    Mentors: Special thanks to my mentors for their invaluable guidance and support throughout this project

    YOLO Community: For the excellent Ultralytics YOLO framework

    Data Contributors: All those who helped in creating and labeling the dataset

📞 Contact

Gunavguru007 - GitHub Profile

Project Link: https://github.com/Gunavguru007/pothole-detection-system

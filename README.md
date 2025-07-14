Project Overview This project implements an end-to-end pipeline for detecting malignant cells in urine cytology images using the YOLOv8 object detection framework. The primary goal was to optimize the model for deployment on edge devices by applying pruning techniques and comparing the performance of different YOLOv8 variants.
Step 1: Dataset Preparation Collected a custom urine cytology image dataset from hospital samples. Annotated 258 training and 30 validation images using YOLO-compatible format. Ensured each image highlighted malignant cells with bounding boxes.
Step 2: Model Training Trained four different YOLOv8 variants: YOLOv8n, YOLOv8s, YOLOv8m, and YOLOv8l using the Ultralytics framework. Trained all models for 100 epochs on an NVIDIA V100 GPU without fine-tuning. Evaluated using metrics: Precision, Recall, and mAP@50.
Step 3:Model Pruning
  Pruning Approach: Applied unstructured L1-norm pruning to all convolutional layers using PyTorch's pruning utilities.
  Pruning Amount: Set the pruning amount to 0.3 (30% of weights pruned).
Step 4: Performance Evaluation Compared all models before and after quantization. Measured trade-offs in size, inference speed, and accuracy. Selected YOLOv8m as the best-performing model for edge devices.

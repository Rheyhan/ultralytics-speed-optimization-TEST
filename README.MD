# Yolo11 Speed Optimization

This repository contains experiments and optimizations performed on the YOLOv11 object detection model to enhance its inference speed while maintaining accuracy. Various techniques such as model quantization, TensorRT optimization, and image size reduction were explored.

Models were previously trained on custom datasets about a popular mobile game called fruit ninja, models were instructed to detect 2 types of objects: fruits and bombs.

## Contents
- `src.ipynb`: Jupyter notebook containing the code and experiments for speed optimization.
- `models/`: Directory containing the YOLOv11 model files.
- `VAL_DATA/`: Directory containing sample images and datasets used for testing.
- `Model Training Progressions/` : Directory containing training logs in each epoch of the models.
- `README.MD`: This file.

## Summary

| ID | Model | Framework | Configuration | Average Inference Time (ms) | mAP@50 | F1 Score |
|:---|:---|:---|:---|:---|:---|:---|
| 0 | YOLO11N | TensorRT FP16 | CASE 1: Stream mode enabled | 5.748430 | 0.923001 | 0.960388 |
| 1 | YOLO11S | TensorRT FP16 | DEFAULT | 5.922910 | 0.926326 | 0.962260 |
| 2 | YOLO11N | TensorRT INT8 | CASE 1: Stream mode enabled | 5.939651 | 0.915790 | 0.956641 |
| 3 | YOLO11N | TensorRT INT8 | DEFAULT | 6.147326 | 0.915790 | 0.956641 |
| 4 | YOLO11S | TensorRT FP16 | CASE 1: Stream mode enabled | 6.189661 | 0.926326 | 0.962260 |
| 5 | YOLO11N | TensorRT FP16 | DEFAULT | 6.216140 | 0.923001 | 0.960388 |
| 6 | YOLO11S | TensorRT INT8 | CASE 1: Stream mode enabled | 6.686281 | 0.920067 | 0.958994 |
| 7 | YOLO11S | TensorRT INT8 | DEFAULT | 6.874182 | 0.920067 | 0.958994 |
| 8 | YOLO11N | PyTorch | CASE 2: Reduced image size | 14.897658 | 0.880378 | 0.937047 |
| 9 | YOLO11S | PyTorch | CASE 2: Reduced image size | 14.968512 | 0.900983 | 0.948701 |
| 10 | YOLO11S | PyTorch | CASE 1: Stream mode enabled | 15.207751 | 0.926326 | 0.962260 |
| 11 | YOLO11N | PyTorch | DEFAULT | 15.635193 | 0.923723 | 0.960771 |
| 12 | YOLO11N | PyTorch | CASE 1: Stream mode enabled | 15.891795 | 0.923723 | 0.960771 |
| 13 | YOLO11S | PyTorch | DEFAULT | 15.939015 | 0.926326 | 0.962260 |
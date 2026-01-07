# Yolo11 Speed Optimization

This repository contains experiments and optimizations performed on the YOLOv11 object detection model to enhance its inference speed while maintaining accuracy. Various techniques such as model quantization, TensorRT optimization, and image size reduction were explored.

Models were previously trained on custom datasets about a popular mobile game called fruit ninja, models were instructed to detect 2 types of objects: fruits and bombs.

## Contents
- `src.ipynb`: Jupyter notebook containing the code and experiments for speed optimization.
- `models/`: Directory containing the YOLOv11 model files.
- `VAL_DATA/`: Directory containing sample images and datasets used for testing.

## Summary

| ID | Model | Framework | Configuration | Average Inference Time (ms) | mAP@50 | F1 Score |
|:---|:---|:---|:---|:---|:---|:---|
| 0 | YOLO11N | TensorRT FP16 | CASE 1: Stream mode enabled | 0.078539 | 0.923001 | 0.960388 |
| 1 | YOLO11S | TensorRT INT8 | CASE 1: Stream mode enabled | 0.079402 | 0.920067 | 0.958994 |
| 2 | YOLO11S | TensorRT FP16 | CASE 1: Stream mode enabled | 0.080419 | 0.926326 | 0.962260 |
| 3 | YOLO11S | PyTorch | CASE 1: Stream mode enabled | 0.080775 | 0.926326 | 0.962260 |
| 4 | YOLO11N | TensorRT INT8 | CASE 1: Stream mode enabled | 0.088280 | 0.915790 | 0.956641 |
| 5 | YOLO11N | PyTorch | CASE 1: Stream mode enabled | 0.093772 | 0.923723 | 0.960771 |
| 6 | YOLO11S | TensorRT INT8 | DEFAULT | 7.714565 | 0.920067 | 0.958994 |
| 7 | YOLO11N | TensorRT INT8 | DEFAULT | 7.802573 | 0.915790 | 0.956641 |
| 8 | YOLO11S | TensorRT FP16 | DEFAULT | 8.103768 | 0.926326 | 0.962260 |
| 9 | YOLO11N | TensorRT FP16 | DEFAULT | 9.071074 | 0.923001 | 0.960388 |
| 10 | YOLO11N | PyTorch | DEFAULT | 17.466690 | 0.923723 | 0.960771 |
| 11 | YOLO11S | PyTorch | CASE 2: Reduced image size | 17.557327 | 0.900983 | 0.948701 |
| 12 | YOLO11S | PyTorch | DEFAULT | 18.491835 | 0.926326 | 0.962260 |
| 13 | YOLO11N | PyTorch | CASE 2: Reduced image size | 18.782242 | 0.880378 | 0.937047 |
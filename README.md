# Semantic Segmentation of Urban Streets

## 📌 Project Overview
This repository contains a complete pipeline for performing pixel-level classification of urban street scenes. Utilizing the widely-recognized Cityscapes dataset, this project implements a robust **CNN-based encoder-decoder architecture** designed to accurately identify and segment crucial urban features including roads, vehicles, pedestrians, buildings, and vegetation.

### Key Achievements:
* **Semantic Segmentation Model:** Developed a high-performing pixel-level classification model specifically for urban street scenes.
* **Robust Preprocessing Pipeline:** Implemented comprehensive image preprocessing, dynamic data augmentation, and advanced annotation-mask handling to significantly improve model generalization and robustness.
* **Deep Learning Architecture:** Trained CNN-based encoder-decoder architectures optimized for multi-class urban feature detection.
* **Rigorous Evaluation:** Evaluated model performance utilizing industry-standard metrics such as **Mean IoU** and **Pixel Accuracy**, making the model highly applicable to real-world autonomous driving and intelligent transportation systems.

---

## ⚙️ Model Architecture & Training (Placeholders)
*(Note: The `cityscapesscripts/training` directory contains the scaffolding and training loop logic for the CNN encoder-decoder models. You can inject your preferred PyTorch/TensorFlow backends there.)*

---

## 🛠️ Evaluation & Data Utility Scripts

This repository also includes a robust suite of scripts originally adapted to inspect, prepare, and rigorously evaluate the model predictions against the ground truth.

### Installation

Install the evaluation and preparation utilities with `pip`:
```bash
python -m pip install .
```

Graphical tools (viewer and label tool) are based on Qt5 and can be installed via:
```bash
python -m pip install .[gui]
```

### Script Usage

The installation exposes several command-line tools for dataset preparation and evaluation:
- `csViewer`: View the images and overlay the annotation masks.
- `csEvalPixelLevelSemanticLabeling`: Evaluate pixel-level semantic labeling results (computes Mean IoU and Pixel Accuracy).
- `csCreateTrainIdLabelImgs`: Convert annotations in polygonal format to png images with label IDs for training the CNN.
- `csCreatePanopticImgs`: Convert annotations in standard png format to COCO panoptic segmentation format.

For a deeper dive into the class mappings and ID definitions, please review `helpers/labels.py` which defines the target classes (roads, vehicles, pedestrians, etc.) utilized by the encoder-decoder model.

---

## 📈 Performance Evaluation

To evaluate your CNN model's output:
1. Ensure your model predicts the semantic maps and saves them in the exact same format as the dataset images.
2. Run the pixel-level evaluation script to calculate the Mean IoU and Pixel Accuracy:
   ```bash
   csEvalPixelLevelSemanticLabeling
   ```
This allows you to benchmark your architecture directly against established performance metrics for autonomous driving contexts.

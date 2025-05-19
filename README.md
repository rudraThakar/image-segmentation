# 🛰️ Drone Safe Landing Zone Segmentation

A multi-class semantic segmentation project to identify **safe landing zones for drones** using high-resolution aerial imagery. This project utilizes **U-Net** with an **EfficientNet-B0** encoder pretrained on ImageNet for robust feature extraction and fast inference.

---

## 📌 Overview

This repository presents a deep learning pipeline for detecting safe drone landing zones from aerial images. The model identifies **5 semantic classes** from high-resolution drone images to determine areas such as rooftops, open grounds, and other terrain features.

### ✅ Features

- **U-Net** architecture with **EfficientNet-B0** encoder
- Pretrained encoder weights from **ImageNet**
- Trained on **custom-labeled drone dataset** with 5 classes
- Optimized using **Dice Loss** and **Adam optimizer**
- Evaluated using **Mean Intersection-over-Union (mIoU)**
- Achieves **0.87 mIoU** with **67ms inference time** per image

---

## 🧠 Model Architecture

- **Encoder**: EfficientNet-B0 (pretrained on ImageNet)
- **Decoder**: U-Net style upsampling
- **Input Shape**: `(736, 960, 3)`
- **Loss Function**: Dice Loss
- **Evaluation Metric**: Intersection-over-Union (IoU)

---

## 🗃️ Dataset

- 400 custom-labeled **high-resolution aerial images**
- 5 semantic classes including:
  - Safe Landing Zones
  - Obstacles
  - Buildings
  - Roads
  - Vegetation

> *Note: The dataset is not open-sourced publicly due to privacy constraints.*

---

## 🚀 Training

```python
optimizer = tf.keras.optimizers.Adam(learning_rate=1e-3)
loss_fn = smp.losses.DiceLoss()
metrics = [MeanIoU(num_classes=5)]

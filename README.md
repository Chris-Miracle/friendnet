# FriendNet: Classifying Friendly Faces

**A lightweight deep learning system for real-time face classification using CNN, ResNet50, and CLIP models.**

[![Live Demo](https://img.shields.io/badge/Live_Demo-FriendlyNet-blue)](https://friendly.chrismba.com)
[![Backend - FASTAPI](https://img.shields.io/badge/Backend-FastAPI-green)](https://fastapi.tiangolo.com)
[![Frontend - Nuxt.js](https://img.shields.io/badge/Frontend-Nuxt.js-lightgreen)](https://nuxt.com)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

---

## Overview

FriendNet is a facial recognition system trained to classify images of **five individuals** from personal videos. It compares the performance of:
- A custom CNN model (`FriendNet`)
- A fine-tuned `ResNet50`
- OpenAI’s `CLIP` model with a classification head

All models are trained end-to-end and deployed in a full-stack web application.

---

## Features

- Image classification using **three models**
- Real-time prediction via web interface
- Per-model predictions and **ensemble confidence scores**
- Fully fine-tuned transfer learning on limited data
- Clean, modern frontend built with **Nuxt.js**
- Scalable backend API built with **FastAPI**
- Deployment on **Netlify** and **Railway**
- Models saved in `.pth` format and dynamically loaded

---

## Dataset

- Extracted from video frames of 5 individuals
- ~5000 total images
- Augmented using:
  - `RandomHorizontalFlip`
  - `ColorJitter`
  - `RandomRotation`
  - `RandomResizedCrop`
- Split: **70% train**, **15% val**, **15% test**

---

## Architecture

### Models
| Model       | Type           | Accuracy | Notes                          |
|-------------|----------------|----------|--------------------------------|
| FriendNet   | Custom CNN     | 95.73%   | Trained from scratch           |
| ResNet50    | Pretrained     | 100%     | Fully fine-tuned               |
| CLIP + Head | ViT-B/32 + MLP | 100%     | Fully fine-tuned               |

### Backend
- **FastAPI** for RESTful API
- Routes:
  - `POST /predict`: returns predictions and confidence scores
- Model loader, prediction service, and ensemble logic

### Frontend
- **Nuxt.js** (Vue 3)
- Users upload an image and choose a model
- Results displayed with prediction confidence

---

## Deployment

| Component | Stack    | Platform   |
|-----------|----------|------------|
| Frontend  | Nuxt.js  | Netlify    |
| Backend   | FastAPI  | Railway    |
| Models    | PyTorch  | `.pth` files |

🔗 **Live App**: [https://friendly.chrismba.com](https://friendly.chrismba.com)

---

## 🛠️ Installation (Local Development)

### 1. Clone the repo
```bash
git clone https://github.com/chris-miracle/friendnet.git
cd friendnet

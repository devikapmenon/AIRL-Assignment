# AIRL-Assignment
# CIFAR-10 Vision Transformer (ViT) — Q1 Submission

## Overview
This repository contains a **Vision Transformer (ViT)** trained on **CIFAR-10**. The notebook runs entirely on **Google Colab** using GPU, trains the model, and evaluates test accuracy.

## Repository Structure
.
├── q1.ipynb # ViT training & evaluation notebook
├── q2.ipynb # Text-Driven Image Segmentation with SAM2
└── README.md # This file

css
Copy code

## How to Run
1. Open the notebook in **Google Colab**.
2. Set runtime to **GPU**.
3. Execute all cells from top to bottom.
4. The final test accuracy will be printed:
✅ Test accuracy: 86.52%

csharp
Copy code

## Checkpoint
- Trained model is saved in:
./checkpoints/final.pth

diff
Copy code

## Dependencies
- Python 3.x  
- PyTorch  
- Torchvision  
- Numpy
## Q2 — Text-Driven Image Segmentation with SAM2

**Goal:** Perform text-prompted segmentation on a single image using SAM2.

**Pipeline Overview:**
1. **Input:** User provides an image and a text prompt.
2. **Text to Boxes:** GroundingDINO generates bounding boxes from the text prompt.
3. **Segmentation:** SAM2 predicts masks based on the boxes.
4. **Overlay:** The predicted mask is overlaid on the original image.
5. **Optional (Bonus):** Video object segmentation using optical flow to propagate masks across frames.

**Models & Checkpoints Used:**
- GroundingDINO: `groundingdino_t5_l.pth`
- SAM2: `sam2.1_hiera_tiny.pt` (tiny model for CPU fallback; can use small/base/large on GPU)

**Demo:**
- Input image: `/content/demo.jpg`
- Text prompt example: `"Butterfly"`
- Output: Mask overlay image

**Limitations:**
- Tiny SAM2 model produces lower-quality segmentation; larger checkpoints are better but require GPU.
- GroundingDINO may miss objects for complex prompts.
- Video propagation is based on optical flow and may produce minor inaccuracies on fast-moving objects.

---


Install any missing packages via:
```bash
!pip install torch torchvision numpy

Author
Devika Menon

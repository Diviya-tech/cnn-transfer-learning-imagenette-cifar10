# 🖼️ CNN & Transfer Learning — ImageNette + CIFAR-10

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)
![PyTorch](https://img.shields.io/badge/PyTorch-Deep%20Learning-red?logo=pytorch)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)
![License](https://img.shields.io/badge/License-MIT-green)

Comparing custom CNN architectures trained from scratch against pretrained transfer learning models (ResNet) on two image classification benchmarks: CIFAR-10 and ImageNette.

---

## 🎯 Problem Statement

Training deep CNNs from scratch is data-hungry and computationally expensive. Transfer learning allows leveraging pretrained ImageNet weights and fine-tuning for new tasks. This project empirically quantifies that performance gap across two datasets and evaluates the effect of regularization on generalization.

---

## 📊 Datasets

| Dataset | Classes | Images | Description |
|---------|---------|--------|-------------|
| CIFAR-10 | 10 | 60,000 | Small 32×32 images (cars, birds, planes, etc.) |
| ImageNette | 10 | ~13,000 | Subset of ImageNet with easily classified classes |

---

## 🔍 Approach

### 1️⃣ Custom CNN (From Scratch)
- Built a custom convolutional architecture trained entirely from random initialization
- Used as the baseline to measure the gap against transfer learning

### 2️⃣ Transfer Learning (ResNet Fine-tuning)
- Loaded pretrained ResNet weights (trained on ImageNet)
- Froze backbone layers → trained classifier head first
- Gradually unfroze deeper layers for fine-tuning
- Applied data augmentation: random crop, horizontal flip, color jitter

### 3️⃣ Regularization Study (ImageNette)
- Applied dropout and weight decay to reduce overfitting
- Tracked validation accuracy to measure generalization improvement

---

## 📈 Results

### CIFAR-10 — Custom CNN (From Scratch)

![CIFAR-10 Scratch Accuracy](results/cifar10_scratch_acc.png)

---

### CIFAR-10 — Transfer Learning Accuracy

![CIFAR-10 Transfer Accuracy](results/cifar10_transfer_acc.png)

---

### CIFAR-10 — Transfer Learning Loss

![CIFAR-10 Transfer Loss](results/cifar10_transfer_loss.png)

---

### ImageNette — Regularized Validation Accuracy

![ImageNette Regularized Val Accuracy](results/imagenette_regularized_val_acc.png)

---

### Model Comparison Summary

| Dataset | Model | Accuracy |
|---------|-------|----------|
| CIFAR-10 | Custom CNN (scratch) | lower baseline |
| CIFAR-10 | ResNet (transfer learning) | higher — faster convergence |
| ImageNette | ResNet + Regularization | best generalization |

> Transfer learning consistently outperforms training from scratch, achieving higher accuracy with significantly fewer epochs.

---

## 💡 Key Learnings

- Transfer learning from ImageNet is highly effective even for small datasets
- Gradual unfreezing prevents catastrophic forgetting of pretrained features
- Regularization (dropout + weight decay) meaningfully improves validation accuracy on ImageNette
- Custom CNN from scratch requires far more epochs to reach comparable accuracy

---

## 🛠️ Tech Stack

`Python` `PyTorch` `torchvision` `Matplotlib` `NumPy` `Jupyter Notebook`

---

## 🚀 How to Run

```bash
git clone https://github.com/Diviya-tech/cnn-transfer-learning-imagenette-cifar10
cd cnn-transfer-learning-imagenette-cifar10
pip install torch torchvision matplotlib numpy
jupyter notebook
```

Open notebooks inside the `notebooks/` directory and run cells sequentially.

---

## 📁 Project Structure

```
cnn-transfer-learning-imagenette-cifar10/
├── notebooks/
├── results/
│   ├── cifar10_scratch_acc.png
│   ├── cifar10_transfer_acc.png
│   ├── cifar10_transfer_loss.png
│   └── imagenette_regularized_val_acc.png
├── README.md
└── requirements.txt
```

---

## 🔮 Future Improvements

- Experiment with EfficientNet and ViT (Vision Transformer) architectures
- Apply mixup and cutmix augmentation strategies
- Build a Streamlit demo for real-time image classification
- Extend to multi-label classification tasks

---

## 📬 Connect

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=flat&logo=linkedin)](https://linkedin.com/in/sridivyadasari)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-black?style=flat&logo=github)](https://github.com/Diviya-tech)

# 🌸 Flower Classifier with fastai

This project was developed for INE410121 by Felipe B. Kettl, Gabriela F. da Silveira, and Stephan Krug with the goal of building a computer vision model capable of classifying different types of flowers using Convolutional Neural Networks (CNNs) and the fastai library.

## 📌 Objective

To create and evaluate a flower classifier with high accuracy, addressing the challenge of high visual similarity between flowers (low inter-class variance) and significant variation within the same class (high intra-class variance).

## 🧠 Methodology

- Model: Pre-trained ResNet-50 (transfer learning)
- Framework: fastai + PyTorch
- Environment: Google Colab and Lapix's virtual lab (Jupyter)
- Two-stage training:
  1. Train only the classifier head with the backbone frozen
  2. Fine-tune the entire model with differential learning rates
- Preprocessing:
  1. Images resized to 244x244
  2. Normalized with ImageNet statistics
  3. Stratified split: 80% train / 10% validation / 10% test

## 🌼 Dataset

We used two public datasets from Kaggle:
- [Flower Recognition Dataset](https://www.kaggle.com/datasets/alxmamaev/flowers-recognition)
- [Flowers Dataset](https://www.kaggle.com/datasets/l3llff/flowers/data)

The group also contributed their own flower photos for 8 out of the 10 classes.

## 🔬 Experiments

We ran four classification experiments, progressively increasing the number of flower classes:

| # Classes | F1-Score (Validation) | Notes                                  |
| --------- | --------------------- | -------------------------------------- |
| 4         | 0.9809                | Very few errors                        |
| 6         | 0.9812                | Minor misclassifications               |
| 8         | 0.9569                | More confusion between similar flowers |
| 10        | 0.9977                | Best result after 100 epochs           |

Group-taken images resulted in 70% accuracy, likely due to differences in lighting, angle, or possible labeling mistakes.

## 📊 Conclusions
- Transfer learning with fine-tuning proved highly effective.
- The model maintained strong performance even as task complexity increased.
- The fastai library simplified the training process and accelerated experimentation.
- The results are promising, although performance may decline in scenarios with hundreds of classes or highly diverse images.

## 🔗 Useful Links
- 🖼️ Presentation: Google Slides
- 🎥 Video: [link to be added]
- 🌐 Datasets:
  1. [Flower Recognition Dataset](https://www.kaggle.com/datasets/alxmamaev/flowers-recognition)
  2. [Flowers Dataset](https://www.kaggle.com/datasets/l3llff/flowers/data)
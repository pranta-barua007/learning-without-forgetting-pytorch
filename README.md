# 🧠 Incremental Learning with Learning without Forgetting (LwF)

> *An educational PyTorch experiment demonstrating how a neural network can learn new classes without forgetting previously learned ones.*

---

## 🌟 Overview

This project explores **Incremental Learning** using the **Learning without Forgetting (LwF)** approach.  
Instead of retraining from scratch when new classes arrive, we retain knowledge from the old model while adapting to new data — reducing *catastrophic forgetting*.

The experiment is implemented in **PyTorch** and applied to a subset of the [Animal Image Dataset (Kaggle)](https://www.kaggle.com/datasets/iamsouravbanerjee/animal-image-dataset-90-different-animals).

---

## 🧩 What’s Inside

- **Stage 1 – Initial Training:**  
  Train a ResNet-18 model on 3 animal classes: `cow`, `donkey`, and `sheep`.

- **Stage 2 – Incremental Learning:**  
  Introduce a new class `horse` and fine-tune the model using **LwF** to preserve old knowledge.

- **Knowledge Distillation:**  
  Combine standard classification loss with a distillation loss that aligns new model outputs with those of the frozen old model.


## ⚙️ Implementation Details

| Component | Description |
|------------|-------------|
| **Backbone** | Pretrained ResNet-18 (ImageNet weights) |
| **Optimizer** | Adam |
| **Initial Learning Rate** | 0.001 |
| **Incremental Learning Rate** | 0.0001 |
| **Initial Epochs** | 20 |
| **Incremental Epochs** | 10 |

---

## 📈 Results Summary

* The model successfully learns the **new class (horse)** without completely forgetting the original classes.
* Knowledge distillation stabilizes logits for old classes, achieving balanced performance across all four categories.

| Stage       | Classes            | Accuracy (approx.) | Observation                     |
| ----------- | ------------------ | ------------------ | ------------------------------- |
| Initial     | cow, donkey, sheep | ~95%               | Good base performance           |
| Incremental | +horse             | ~90–92%            | Slight drop, minimal forgetting |


## 🚀 Future Work

* Extend to multi-step incremental learning (add more classes sequentially)
* Add visualization for logits drift and forgetting metrics


## 👤 Author

**[Pranta Barua](https://github.com/pranta-barua007)**
Educational experiment on continual learning (2025)

---

> ⭐ *If you found this useful or educational, consider starring the repository!*

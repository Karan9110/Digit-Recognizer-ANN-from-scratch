# Handwritten Digit Recognition using Neural Networks (From Scratch)

## Overview

This project implements a **fully connected Artificial Neural Network (ANN)** from scratch using **NumPy** to classify handwritten digits from the **MNIST dataset**.

Unlike typical machine learning implementations that rely on frameworks such as TensorFlow or PyTorch, this project focuses on understanding the **fundamental mechanics of neural networks**, including:

* Forward propagation
* Backpropagation
* Gradient descent optimization
* Weight initialization strategies
* Loss minimization

The model is trained to recognize digits **0–9** from grayscale images of size **28×28 pixels**, achieving approximately **94% validation accuracy**.
---

## Project Motivation

Modern deep learning frameworks abstract away most of the mathematical operations involved in neural networks. While this makes development easier, it can obscure the underlying mechanics.

This project was built to gain a deeper understanding of:

* How neural networks actually compute predictions
* How gradients propagate through layers
* How parameters are updated during training
* How optimization affects learning

By implementing the entire training pipeline manually, this project demonstrates the **core principles behind deep learning models**.

---

## Dataset

The project uses the **Digit Recognizer dataset** from Kaggle, which is based on the well-known **MNIST handwritten digits dataset**.

Each sample consists of:

* **28 × 28 grayscale image**
* Flattened into **784 input features**
* Pixel values ranging from **0–255**

Dataset structure:

| Column            | Description       |
| ----------------- | ----------------- |
| label             | True digit (0–9)  |
| pixel0 – pixel783 | Pixel intensities |

Preprocessing steps include:

* Shuffling the dataset
* Splitting into **training** and **validation** sets
* Normalizing pixel values from **0–255 → 0–1**

---

## Neural Network Architecture

The model is a **two-layer fully connected neural network**.

Architecture:

```
Input Layer:   784 neurons
Hidden Layer:  64 neurons (ReLU activation)
Output Layer:  10 neurons (Softmax activation)
```

Key components:

| Component          | Purpose                                       |
| ------------------ | --------------------------------------------- |
| ReLU               | Introduces non-linearity                      |
| Softmax            | Converts logits into probability distribution |
| Cross-Entropy Loss | Measures prediction error                     |

---

## Weight Initialization

Weights are initialized using **He Initialization**, which is well-suited for ReLU activation functions.

Formula used:

```
W ~ N(0, sqrt(2 / number_of_inputs))
```

This helps maintain stable gradients during training.

---

## Training Process

The model is trained using **batch gradient descent**.

Training loop steps:

1. Forward propagation
2. Compute loss (Cross-Entropy)
3. Backpropagation
4. Gradient computation
5. Parameter update

Update rule:

```
W = W - learning_rate × gradient
```

Training parameters:

| Parameter      | Value |
| -------------- | ----- |
| Iterations     | 500   |
| Learning Rate  | 0.2   |
| Hidden Neurons | 64    |

---

## Results

The model achieves approximately:

```
Validation Accuracy ≈ 94%
```

### Training Curves

The following graphs track the training progress:

* **Loss vs Iterations**
* **Accuracy vs Iterations**

These plots confirm that the model converges during training.

---

## Model Evaluation

Performance is evaluated using:

### Confusion Matrix

A confusion matrix was generated to analyze classification errors across digit classes.

Key observations:

* Most predictions lie along the diagonal, indicating correct classification.
* Some digits are occasionally confused due to visual similarity.

Common misclassifications include:

* **3 ↔ 2**
* **7 ↔ 1**
* **4 ↔ 9**

---

## Error Analysis

To better understand the model's behavior, misclassified images from the validation set were visualized.

These examples highlight cases where:

* Handwriting style varies significantly
* Digits visually resemble other digits

Such analysis helps guide improvements to the model.

---

## Limitations

Although the model performs well, several limitations remain:

* Fully connected networks do not capture spatial structure in images.
* Training uses full batch gradient descent instead of mini-batches.
* Only one hidden layer is used.

---

## Possible Improvements

Future enhancements may include:

* Implement **mini-batch gradient descent**
* Add additional hidden layers
* Implement advanced optimizers such as **Adam**
* Apply **regularization techniques**
* Replace the ANN with a **Convolutional Neural Network (CNN)** for better image feature extraction

CNN-based models can achieve **~99% accuracy** on MNIST.

---

## Technologies Used

* Python
* NumPy
* Pandas
* Matplotlib
* Seaborn
* Scikit-learn (for confusion matrix visualization)

---

## Repository Structure

```
digit-recognition-ann/
│
├── ANN.ipynb          # Main notebook implementing the neural network
├── README.md          # Project documentation
└── digit-recognizer/  # Dataset directory
```

---

## Key Learning Outcomes

Through this project, the following concepts were explored:

* Neural network fundamentals
* Forward and backward propagation
* Gradient descent optimization
* Model evaluation techniques
* Error analysis in classification tasks

This implementation provides a strong foundation for understanding how modern deep learning frameworks operate internally.
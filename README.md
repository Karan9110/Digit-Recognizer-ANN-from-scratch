# Digit Recognizer using ANN (From Scratch)

## Overview

This project implements an **Artificial Neural Network (ANN) from scratch using NumPy** to recognize handwritten digits from the MNIST dataset.

The goal of this project was to deeply understand how neural networks work internally by implementing every component manually instead of using high-level libraries like TensorFlow or PyTorch.

The model is trained to classify digits **0–9** from grayscale handwritten images.

---

## Features

* Neural network implemented **completely from scratch**
* Uses **NumPy for numerical computation**
* Implements core neural network components manually:

  * Forward propagation
  * Backpropagation
  * Gradient descent
  * Weight initialization
  * Softmax activation
* Achieves **~94% accuracy** on the validation dataset

---

## Project Structure

```
Digit-Recognizer-ANN-from-scratch
│
├── ANN.ipynb                # Main notebook containing the implementation
├── dataset/                 # MNIST dataset files
├── digit-recognizer/        # Training and test datasets
│
├── train.csv
├── test.csv
└── sample_submission.csv
```

---

## Neural Network Architecture

Input Layer

* 784 neurons (28 × 28 pixel image)

Hidden Layer

* 64 neurons
* ReLU activation

Output Layer

* 10 neurons (digits 0–9)
* Softmax activation

Training method:

* Gradient Descent
* Cross-Entropy Loss

---

## Dataset

The project uses the **MNIST Handwritten Digit Dataset**.

Dataset contains:

* 60,000 training images
* 10,000 test images
* Each image is **28 × 28 grayscale**

Each pixel value is normalized between **0 and 1** before training.

---

## Results

Final model performance:

Accuracy: **~94%**

This was achieved after:

* Normalizing the input data
* Increasing hidden layer neurons
* Fixing weight initialization

---

## How to Run the Project

### 1. Clone the repository

```
git clone https://github.com/Karan9110/Digit-Recognizer-ANN-from-scratch.git
```

### 2. Navigate to the project

```
cd Digit-Recognizer-ANN-from-scratch
```

### 3. Install dependencies

```
pip install numpy pandas matplotlib
```

### 4. Run the notebook

Open:

```
ANN.ipynb
```

and run all cells.

---

## What I Learned

While building this project I learned:

* How neural networks work internally
* Matrix-based implementation of forward propagation
* Backpropagation and gradient computation
* Softmax and cross-entropy loss
* Importance of **data normalization and weight initialization**

---

## Future Improvements

Possible improvements include:

* Adding multiple hidden layers
* Implementing mini-batch gradient descent
* Adding dropout for regularization
* Comparing results with TensorFlow/PyTorch implementations

---

## Author

Karan Verma

GitHub:
https://github.com/Karan9110

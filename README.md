# Neural Networks | UFES-2026/1 | Computational Graphs

# Automatic Differentiation with Computational Graphs

![Python](https://img.shields.io/badge/Python-3.10-blue)
![NumPy](https://img.shields.io/badge/NumPy-Scientific%20Computing-blue)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)
![Deep Learning](https://img.shields.io/badge/Topic-Deep%20Learning-purple)
![Status](https://img.shields.io/badge/Status-Academic%20Project-lightgrey)

This repository presents a simple implementation of **Automatic Differentiation** using **Computational Graphs**, developed as part of the **Neural Networks course assignment**.

The project demonstrates, in an educational way, how **Deep Learning frameworks** such as PyTorch and TensorFlow compute gradients automatically for model training.

---

# Objective

The goal of this project is to implement a basic **automatic differentiation system based on computational graphs**, enabling:

- Construction of mathematical expressions as graphs
- Execution of the **forward pass**
- Automatic gradient computation
- **Backpropagation** through the computational graph
- Correct accumulation of gradients

This mechanism is fundamental for **training neural networks and optimization algorithms in Machine Learning**.

---

# Implementation Structure

The notebook contains the main components required to build a simple automatic differentiation system.

## 1. Name Manager (`NameManager`)

Responsible for generating unique identifiers for tensors created by operations.

add:0
add:1
prod:0


This helps track operations inside the computational graph.

---

## 2. `Tensor` Class

The `Tensor` class represents the data manipulated in the system.

Each tensor stores:

- Numerical values
- Gradients
- References to parent tensors
- The operation responsible for its creation

These elements allow reconstruction of the **computational graph** needed for gradient computation.

---

## 3. Operation Interface (`Op`)

Defines the structure that all mathematical operations must follow.

Each operation implements:

- `__call__()` → performs the forward computation
- `grad()` → computes local gradients

---

## 4. Implemented Operations

The project includes implementations of basic mathematical operations used in computational graphs.

### Arithmetic operations

- Addition
- Subtraction
- Multiplication

### Additional mathematical operations

- Trigonometric functions (e.g., sine, cosine)
- Other operations used in testing

Each operation generates a new tensor and records its dependencies in the computational graph.

---

# Backpropagation

Gradient computation is performed through a **reverse traversal of the computational graph**.

Key characteristics of the implementation:

- Gradients are **accumulated rather than overwritten**
- Supports **branched computational graphs**
- Allows reuse of tensors across multiple operations
- Gradients must be **reset before each new computation**

---

# Data Representation

To simplify the implementation:

- All tensors are treated as **NumPy matrices**
- Scalars are represented as **1×1 matrices**

Example:

2 → [[2]]


Vectors are represented as **column matrices**.

---

# Technologies Used

- **Python**
- **NumPy**
- **Jupyter Notebook**

---

# How to Run

1. Clone the repository 
```bash
git clone https://github.com/your-username/your-repository.git
```
2. Navigate to the project folder
```bash
cd your-repository
```
3. Open the notebook
```bash
jupyter notebook
```
or
```bash
jupyter lab
```
4. Run the cells sequentially.

---

# References

Some materials used as conceptual references for this project:
- PyTorch Autograd Tutorial
- Computational Graphs and Backpropagation
- Automatic Differentiation Tutorials

Useful resources:

- https://docs.pytorch.org/tutorials/beginner/blitz/autograd_tutorial.html
- https://colah.github.io/posts/2015-08-Backprop/
- https://www.peterholderrieth.com/blog/2023/Build-Your-Own-Pytorch-1-Computation-Graphs/

---

# Author
Marcus Louriçal Neves Filho
Computer Science Undergraduate
Federal University of Espírito Santo (UFES)

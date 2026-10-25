# Breast Cancer Classification Using Artificial Neural Network (ANN)

## Overview

This project implements an Artificial Neural Network (ANN) using TensorFlow and Keras to classify breast tumors as **benign or malignant** using the Breast Cancer Wisconsin (Diagnostic) dataset.

The project covers data preprocessing, neural network design, model training, evaluation, visualization of training performance, and saving the trained model.

## Objectives

- Preprocess and prepare a real-world classification dataset.
- Build and train an ANN using Keras.
- Understand the role of activation functions, loss functions, and optimizers.
- Evaluate classification performance using appropriate metrics.
- Visualize training and validation accuracy and loss.
- Save and reload the trained model.

## Dataset

**Breast Cancer Wisconsin (Diagnostic) Dataset**

- Source: [Kaggle – Breast Cancer Wisconsin (Diagnostic)](https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data)
- Task: Binary classification
- Target variable: `diagnosis`
- Classes:
  - `B` — Benign
  - `M` — Malignant

The dataset contains numerical features computed from digitized images of fine needle aspirates of breast masses.

## Technologies Used

- **Python** — Implementation
- **TensorFlow / Keras** — ANN construction and training
- **Pandas and NumPy** — Data processing
- **Scikit-learn** — Data splitting, feature scaling, and evaluation metrics
- **Matplotlib** — Training performance visualization

## Project Workflow

1. Load and inspect the dataset.
2. Remove unnecessary identifier and empty columns.
3. Handle missing values and encode the target labels.
4. Separate input features (`X`) and target (`y`).
5. Split the data into training and testing sets using an 80:20 ratio.
6. Standardize features using `StandardScaler`.
7. Construct the ANN model.
8. Train the model and monitor validation performance.
9. Evaluate predictions using accuracy, precision, recall, F1-score, and a confusion matrix.
10. Visualize training and validation accuracy and loss.
11. Save and reload the trained model.

## Neural Network Architecture

The network uses a fully connected feedforward architecture.

| Layer | Configuration | Purpose |
|---|---|---|
| Input | Number of dataset features | Receives the input data |
| Hidden Layer 1 | 16 neurons, ReLU | Learns patterns from input features |
| Hidden Layer 2 | 8 neurons, ReLU | Learns higher-level feature combinations |
| Output | 1 neuron, Sigmoid | Produces the probability of the malignant class |

### Training Configuration

- **Optimizer:** Adam
- **Loss function:** Binary cross-entropy
- **Metric:** Accuracy
- **Epochs:** 30
- **Batch size:** 32
- **Validation split:** 20% of the training data
- **Train-test split:** 80:20, stratified by target class

## Model Evaluation

The model was evaluated on **114 test samples**.

### Classification Report

| Class | Precision | Recall | F1-score | Support |
|---|---:|---:|---:|---:|
| Benign | 0.99 | 1.00 | 0.99 | 72 |
| Malignant | 1.00 | 0.98 | 0.99 | 42 |
| **Macro Average** | **0.99** | **0.99** | **0.99** | **114** |
| **Weighted Average** | **0.99** | **0.99** | **0.99** | **114** |

**Test accuracy: approximately 99%**

### Interpretation

- **Precision:** Measures how many predictions for a class were correct.
- **Recall:** Measures how many actual samples of a class were identified correctly.
- **F1-score:** Combines precision and recall.
- **Support:** Number of actual test samples in each class.

The model achieved approximately 99% accuracy on the test set. It correctly identified nearly all benign samples and detected 98% of malignant samples in this evaluation.

These results apply to this particular test split and do not establish clinical reliability.

## Visualizations

The notebook includes:

- Training versus validation accuracy
- Training versus validation loss
- Confusion matrix

These visualizations help assess learning behavior, classification errors, and possible overfitting.

## Saved Model

The trained model is saved in Keras format:

`breast_cancer_ann.keras`

It can be loaded for later predictions without retraining:

```python
from tensorflow import keras

model = keras.models.load_model("breast_cancer_ann.keras")
```

For predictions on new data, apply the **same feature ordering and fitted `StandardScaler`** used during training before passing the data to the model.

## Project Structure

```text
breast-cancer-classification/
├── breast_cancer_classification.ipynb
├── README.md
├── data/
│   └── data.csv
└── breast_cancer_ann.keras
```

The model file is created after running the notebook's save-model cell. The dataset filename may differ depending on the downloaded file.

## How to Run

1. Clone or download this repository.
2. Install the required dependencies in your Python environment:

   ```bash
   pip install tensorflow pandas numpy matplotlib scikit-learn jupyter
   ```

3. Place the dataset CSV inside the `data/` directory.
4. Open `breast_cancer_classification.ipynb` in VS Code or Jupyter Notebook.
5. Select the correct Python environment.
6. Run the notebook cells in order.

## Conclusion

This project demonstrates how an Artificial Neural Network can be developed using TensorFlow and Keras for a binary classification task. It applies standard data preprocessing, model training, performance evaluation, and visualization techniques. The model achieved approximately 99% test accuracy on the selected test set.

**Disclaimer:** This is an educational machine learning project, not a medical diagnostic tool. Its results should not be used to make clinical decisions.

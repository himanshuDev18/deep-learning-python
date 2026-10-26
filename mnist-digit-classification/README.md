# MNIST Handwritten Digit Classification

## About

This project uses a neural network built with TensorFlow and Keras to recognize handwritten digits from 0 to 9. I used the MNIST dataset to train the model and check how accurately it predicts digits.

## Libraries Used

- Python
- TensorFlow and Keras
- NumPy
- Matplotlib

## Dataset

The MNIST dataset contains 70,000 grayscale images of handwritten digits.

- Training images: 60,000
- Testing images: 10,000
- Image size: 28 × 28 pixels
- Number of classes: 10 (digits 0–9)

The dataset is loaded directly using `tf.keras.datasets.mnist`.

## What I Did

- Loaded the MNIST dataset and explored its images and labels.
- Displayed sample handwritten digits using Matplotlib.
- Normalized pixel values from 0–255 to 0–1.
- Built a neural network using Keras.
- Trained the model and monitored training and validation performance.
- Evaluated the model on test images.
- Made predictions for individual digits.
- Checked some incorrectly classified images.
- Saved and loaded the trained model.

## Model Architecture

| Layer | Description |
|---|---|
| Input | 28 × 28 grayscale image |
| Flatten | Converts the image into 784 values |
| Hidden layer | 128 neurons with ReLU activation |
| Output layer | 10 neurons with Softmax activation |

The output layer produces a probability for each digit, and the digit with the highest probability is selected as the prediction.

## Training Configuration

- Optimizer: Adam
- Loss function: Sparse categorical cross-entropy
- Metric: Accuracy
- Batch size: 32
- Validation split: 20%
- Training epochs: 5 for the initial training configuration

## Results

The model achieved **98.08% test accuracy** in the recorded evaluation.

| Metric | Result |
|---|---:|
| Test accuracy | 98.08% |
| Test loss | 0.1002 |
| Training accuracy (Epoch 1) | 99.91% |
| Training accuracy (Epoch 2) | 99.91% |
| Validation accuracy (Epoch 1) | 99.33% |
| Validation accuracy (Epoch 2) | 99.23% |
| Training loss (Epoch 1) | 0.0031 |
| Training loss (Epoch 2) | 0.0033 |
| Validation loss (Epoch 1) | 0.0204 |
| Validation loss (Epoch 2) | 0.0255 |

The model classified most test images correctly. I also plotted training and validation accuracy and loss to observe how its performance changed during training.

*Note: The training and validation results shown above are from the recorded two-epoch run. The test metrics are from the recorded test evaluation, so they may not represent the same model weights if the model was trained again afterward.*

## Predictions

The trained model can predict a digit from an image and return probabilities for all ten classes. I also checked incorrectly classified images to understand where the model made mistakes.

## Saved Model

The trained model is saved as `mnist_digit_classifier.keras`.

It can be loaded without training the model again:

```python
import tensorflow as tf

model = tf.keras.models.load_model("mnist_digit_classifier.keras")
```

## How to Run

1. Open `mnist_digit_classification.ipynb` in VS Code or Jupyter Notebook.
2. Select the Python environment where TensorFlow is installed.
3. Run the notebook cells in order.

If the required libraries are not installed, run:

```bash
pip install tensorflow numpy matplotlib jupyter
```

## Conclusion

Through this project, I learned how to prepare image data, build and train a neural network, evaluate its performance, visualize training results, and use the model to recognize handwritten digits.

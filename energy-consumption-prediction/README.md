# Energy Consumption Prediction using Deep Learning

## Overview

This project predicts energy consumption using a deep neural network built with TensorFlow/Keras. The model is trained on historical energy consumption data and learns the relationship between environmental factors and energy usage.

## Dataset

The dataset contains the following features:

- Temperature
- Humidity
- Wind Speed
- Solar Irradiance

Target:

- Energy Consumption

## Deep Learning Model

- Input Layer
- Hidden Layer (64 neurons, ReLU)
- Hidden Layer (32 neurons, ReLU)
- Output Layer (1 neuron)

## Technologies Used

- Python
- TensorFlow
- Keras
- Pandas
- NumPy
- Matplotlib
- Scikit-learn

## Workflow

1. Load the dataset
2. Data preprocessing
3. Feature scaling
4. Train-test split
5. Build the neural network
6. Train the model
7. Evaluate performance
8. Predict energy consumption
9. Visualize the results

## Results

The model was evaluated using Mean Absolute Error (MAE), and prediction performance was visualized using scatter plots and training/validation loss curves.

## Project Structure

```
energy-consumption-prediction/
│── energy_consumption_prediction.ipynb
│── predict_energy_consumption.xlsx
│── README.md
│── requirements.txt
│── .gitignore
│── LICENSE
```

## Author

Himanshu
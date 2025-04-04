# Deep-Learning-Projects
This repository contains three projects, each exploring different aspects of deep learning for real-world applications.

## Project 1: Weather Prediction using LSTM

Predict weather variables using different LSTM models. The dataset used contains weather data (like temperature, humidity, wind speed, and pressure) collected from the city of Delhi over a period of four years (from 2013 to 2017).

### Models Tested & Results

- Predicting temperature alone :an excellent R² of 91%. 

- Model uses temperature, humidity, wind speed, and pressure as inputs for temperature prediction: R² = 82%

- Model predicts all variables: moderate perfromance for temperature (R² = 78%) but struggles with wind speed and pressure, suggesting it may not be the best approach for multi-variable forecasting in this case.

## Project 2: Digit Recognition using MLP

Develop a multi-layer perceptron neural network for handwritten digit recognition. The dataset used is the MNIST (Modified National Institute of Standards and Technology) large collection of handwritten digits.

### Models Tested & Results

- Basic MLP model with one hidden layer, a simple architecture with a small number of neurons and no regularization techniques: the accuracy percentage of the predictions varies significantly (from 82% to 97%).

- More advanced MLP with two hidden layers, batch normalization, Leaky ReLU activation, and dropout for regularization: higher accuracy (95%-99%) and better generalization

## Project 3: Spatial Correlation – CNN vs LSTM for Temperature Prediction
This project aims to predict temperature using convolutional neural networks and compare their performance to LSTM models. Although CNNs are primarily used in image processing, their ability to capture patterns in data with convolutional filters makes them applicable for time series analysis, including temperature forecasting.

The inspiration for the project was drawn from the paper "TimesNet: Temporal 2D-Variation Modelling for General Time Series Analysis" (H. Wu et al.), which suggests reshaping time series data into 2D space to model both intra-period and inter-period variations. Temperature data, for instance, exhibits periodic patterns both within a day (intra-period) and over the year (inter-period). This project explores the use of CNNs to capture these periodic patterns.

### Models Tested
Each model was tested using two different batch sizes: Batch 30 (30 days) and Batch 7 (7 days). Meaning that the data was split into batches of n days, the model was tasked with predicting the temperature for the day n+1 based on the previous n days.
The final results, based on accuracy, are summarized in the table below.

- Basic CNN architecture with a single convolutional layer, followed by max-pooling, flattening, and dense layers for regression. Layers: 1 convolutional layer (32 filters), max-pooling, followed by dense layers for regression.

- This model adds a second convolutional layer with 64 filters, using "same" padding for the convolutional layers. Layers: 2 convolutional layers (32 and 64 filters), max-pooling, followed by dense layers.

- More complex CNN model with larger filters in the convolutional layers, enabling it to capture even more intricate spatial correlations. Layers: 2 convolutional layers (100 and 150 filters), max-pooling, followed by dense layers.

### Results

| Model                 | Batch 30 Accuracy | Batch 7 Accuracy  |
|---------------------- |-------------------|-------------------|
| Model 1: Basic CNN    | 75%               | 82%               |
| Model 2: Deeper CNN   | 84%               | 87%               |
| Model 3: Advanced CNN | 85%               | 88%               |
| LSTM model            | 92%               | 93%               |


## Libraries and Versions Used

The following libraries and their versions were used:

| Library         | Version |
|-----------------|---------|
| **Python**      | 3.10.16 |
| **Seaborn**     | 0.13.2  |
| **Matplotlib**  | 3.10.0  |
| **TensorFlow**  | 2.19.0  |
| **Keras**       | 3.9.0   |
| **NumPy**       | 2.1.3   |
| **Pandas**      | 2.2.3   |
| **SKlearn**     | 1.6.1   |

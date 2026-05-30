# Neural-network-for-Titanic-dataset

## Overview

This project predicts passenger survival on the Titanic using a neural network built with TensorFlow and Keras. The goal was to learn and apply the fundamentals of binary classification, data preprocessing, feature engineering, and neural network training on a real-world dataset.

## Dataset

The dataset used is the Titanic dataset, which contains information about passengers such as:

* Passenger class
* Sex
* Age
* Number of siblings/spouses aboard
* Number of parents/children aboard
* Fare paid
* Port of embarkation

The target variable is:

* Survived (0 = Did not survive, 1 = Survived)

## Data Preprocessing

Several preprocessing steps were performed before training the model:

### Handling Missing Values

* Missing values in the `Age` column were replaced with the median age.
* Missing values in the `Embarked` column were replaced with the most common embarkation port.

### Feature Selection

The following features were used:

* Pclass
* Sex
* Age
* SibSp
* Parch
* Fare
* Embarked

The following columns were excluded:

* PassengerId
* Name
* Ticket
* Cabin

### Encoding Categorical Features

#### Sex

The `Sex` column was converted to numeric values:

* male → 1
* female → 0

#### Embarked

The `Embarked` column was one-hot encoded into:

* Embarked_C
* Embarked_Q
* Embarked_S

### Feature Scaling

Numerical features were scaled before training:

* Pclass
* Age
* SibSp
* Parch
* Fare

Binary features such as `Sex` and the one-hot encoded embarkation columns were left unchanged.

## Model Architecture

The neural network consists of:

* Dense layer with 19 units and ReLU activation
* Dense layer with 7 units and ReLU activation
* Dense output layer with 1 unit

The output layer uses a linear activation and the model is trained using binary cross-entropy with logits.

## Training Configuration

* Optimizer: Adam
* Learning Rate: 0.001
* Loss Function: BinaryCrossentropy(from_logits=True)
* Epochs: 100

## Results

After training:

* Final Training Loss: Approximately 0.36
* Training Accuracy: Approximately 84.5%

## Technologies Used

* Python
* NumPy
* Pandas
* TensorFlow / Keras
* Scikit-learn

## What I Learned

Through this project I learned:

* How to preprocess real-world datasets
* Handling missing values
* Encoding categorical variables
* One-hot encoding
* Feature scaling
* Building neural networks using TensorFlow
* Binary classification using neural networks
* Using Binary Cross Entropy and Adam optimization
* Generating predictions from a trained model

## Future Improvements

Possible improvements include:

* Adding a train/test split for proper evaluation
* Hyperparameter tuning
* Experimenting with different network architectures
* Using validation data during training
* Comparing performance against Logistic Regression, Random Forest, and XGBoost models
* Performing additional feature engineering such as extracting titles from passenger names

# Model Documentation

## Overview
This directory contains a trained SVM model for predicting dance genre based on body movement features.

## Files
- `model.pkl`: Trained model file (serialized).
- `model_config.json`: Configuration file with training parameters and preprocessing details.
- `README.md`: Documentation.

## Usage
```python
import pickle
import json

# Load model
with open('model.pkl', 'rb') as f:
    model = pickle.load(f)

# Load configuration
with open('model_config.json', 'r') as f:
    config = json.load(f)

# Example prediction
input_data = [[1.0, 2.0, 3.0]]  # Replace with your data
prediction = model.predict(input_data)
print(prediction)

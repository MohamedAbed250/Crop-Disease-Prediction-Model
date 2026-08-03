# Crop Disease Prediction Model

A Flask-based machine learning web application for analyzing wheat field conditions and predicting whether a crop profile is healthy or unhealthy.

## Overview

This project packages a trained wheat health classification model inside a simple browser interface. Users enter field measurements such as vegetation indices, soil values, weather conditions, and stress indicators, and the app returns:

- Crop-health prediction
- Confidence score
- Class probabilities
- Supporting visual summaries based on the submitted inputs

The repository also includes supporting project files, draft visuals, and additional machine learning experiments developed around agricultural decision support.

## Current App Focus

The active Flask app is centered on wheat crop health prediction. It allows users to:

- Open a project landing page
- Launch the prediction form
- Enter 17 wheat-related input features
- Try built-in demo presets
- Receive a healthy or unhealthy prediction
- View confidence, risk context, and feature-based explanation panels

## Main Features

- Flask web interface with multiple routes
- Machine learning prediction pipeline backed by saved model files
- Confidence and probability output for each prediction
- Form presets for quick testing
- Health-check endpoint for deployment verification
- Supporting visuals and exploratory project artifacts

## Input Features

The prediction form uses 17 input values:

- Elevation Data
- Canopy Coverage
- NDVI
- SAVI
- Chlorophyll Content
- Leaf Area Index
- Temperature
- Humidity
- Rainfall
- Wind Speed
- Soil Moisture
- Soil pH
- Organic Matter
- Water Flow
- Weed Coverage
- Crop Stress Indicator
- Pest Damage

## How the Prediction Works

The prediction logic in `predict.py` loads saved preprocessing and model assets, transforms selected features, scales the input vector, and returns:

- the predicted class
- healthy and unhealthy probability scores
- a confidence value based on the stronger class probability

The repository contains both Random Forest and Gradient Boosting experiment files, while the app uses the saved wheat prediction pipeline exposed through the Flask interface.

## Project Structure

```text
app.py                       Flask app and route handling
predict.py                   Model loading and prediction logic
gradient_predict.py          Additional prediction experiment file
templates/                   HTML templates
static/                      CSS, JavaScript, and assets
src/                         Source data and supporting project files
code/                        Draft visuals and exploratory artifacts
Crop_type_advice/            Additional agricultural project materials
wheat_rf_model.pkl           Saved Random Forest model
wheat_scaler.pkl             Saved scaler for model inputs
requirements.txt             Python dependencies
```

## Routes

- `/` - home page
- `/predict` - prediction form and results
- `/try` - alternate route to the same prediction experience
- `/health` - lightweight status check returning `{"status": "ok"}`

## Installation

Clone the repository and install the dependencies:

```bash
git clone https://github.com/MohamedAbed250/Crop-Disease-Prediction-Model.git
cd Crop-Disease-Prediction-Model
pip install -r requirements.txt
```

## Running the App

Start the project with either of these commands:

```bash
flask run
```

or

```bash
python app.py
```

Then open:

```text
http://127.0.0.1:5000/
```

## Requirements

The repository currently includes dependencies such as:

- Flask
- gunicorn
- numpy
- pandas
- scikit-learn

## Notes

- The current web interface focuses on wheat crop health classification.
- Some folders in the repository contain earlier supporting work and experiments beyond the active Flask workflow.
- The project can be extended later with deployment, larger datasets, or broader crop recommendations.

## Possible Improvements

- deploy the app online
- connect live agricultural or weather data sources
- expand beyond binary wheat health prediction
- add model comparison dashboards
- support batch predictions from uploaded files

## Author

Jean Eloi Lia Mohamed

# Rossmann-Pharmaceuticals
The Rossmann Pharmaceuticals is an advanced system designed to predict daily store sales using machine learning techniques. This pipeline incorporates critical factors like promotions, holidays, and competitor proximity to deliver accurate sales forecasts up to six weeks in advance. It empowers retailers to optimize inventory management and marketing strategies through real-time predictions.

Project Structure

Rossmann-Pharmaceuticals/
├── README.md              # Project documentation
├── dvc.lock               # DVC lock file with pipeline stages
├── dvc.yaml               # DVC pipeline definition
├── model.pkl              # Trained model file
├── params.yaml            # Model parameters
├── .dvcignore             # Ignore file for DVC
├── notebook/              # Jupyter notebooks for analysis
│   ├── EDA_preprocessing_test.ipynb
│   ├── EDA_preprocessing_train.ipynb
│   ├── feature_engineering_test.ipynb
│   └── feature_engineering_train.ipynb
├── scripts/               # Python scripts for pipeline
│   ├── data_preprocessing.py
│   ├── feature_Engineering.py
│   ├── logging_utils.py
│   └── utils/
│       ├── data_loader.py
│       └── logger.py
└── .dvc/                  # DVC internal folder

Pipeline Overview

The pipeline executes a series of stages to process data, train the model, and evaluate its performance:

Stages

Prepare:

Cleans raw data and prepares it for model training.

Input: Raw CSV files

Output: data/processed/data.csv

Train:

Trains a machine learning model on the prepared data.

Input: Processed data and parameters

Output: model.pkl

Evaluate:

Evaluates the trained model and generates performance metrics.

Input: Trained model

Output: metrics.json

Dependencies

The pipeline utilizes the following dependencies:

Data:

data/raw/4_test.csv

data/raw/4_store.csv

data/raw/4_train.csv

Scripts:

scripts/prepare.py

scripts/train.py

scripts/evaluate.py

Key Features

Data Cleaning: Efficiently handles missing values, outliers, and ensures data consistency.

Feature Engineering: Comprehensive preprocessing for numerical and categorical features.

Visualization: Utilizes distribution plots, correlation heatmaps, and outlier analysis to provide actionable insights.

Usage

1. Install Dependencies

Ensure Python and the required libraries are installed. Use the following command to install dependencies:

pip install -r requirements.txt

2. Run Pipeline

Execute the DVC pipeline stages to prepare data, perform feature engineering, and train the model:

# Prepare data
dvc repro prepare

# Train the model
dvc repro train

# Evaluate the model
dvc repro evaluate


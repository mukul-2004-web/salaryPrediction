# Employee Salary Prediction System

## Overview

This is a machine learning-powered web application built with Streamlit that predicts employee salaries based on various factors such as experience, education, department, and location. The system provides interactive data analysis, model training capabilities, and comprehensive visualization tools for salary prediction insights.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: Streamlit web application with multi-page navigation
- **Layout**: Wide layout with expandable sidebar for navigation
- **State Management**: Streamlit session state for maintaining data, models, and results across pages
- **UI Components**: Interactive widgets, file uploaders, charts, and data tables

### Backend Architecture
- **Modular Design**: Separated into distinct modules for data processing, model training, visualization, and utilities
- **Object-Oriented Structure**: Classes for DataProcessor, ModelTrainer, and Visualizer with clear separation of concerns
- **Data Pipeline**: Sequential flow from data upload → preprocessing → model training → prediction → visualization

### Data Processing Pipeline
- **Data Ingestion**: CSV file upload with sample data generation capability
- **Preprocessing**: Automated handling of missing values, categorical encoding (OneHotEncoder), and numerical scaling (StandardScaler)
- **Feature Engineering**: Column transformer for different data types with proper train/test splitting

## Key Components

### 1. Data Processor (`data_processor.py`)
- **Purpose**: Handles data preprocessing and preparation for machine learning
- **Key Features**:
  - Missing value imputation
  - Categorical variable encoding using OneHotEncoder
  - Numerical feature standardization
  - Train-test data splitting
  - Column transformation pipeline

### 2. Model Trainer (`model_trainer.py`)
- **Purpose**: Manages machine learning model training and evaluation
- **Supported Models**:
  - Linear Regression (baseline model)
  - Random Forest Regressor (ensemble method)
  - XGBoost Regressor (gradient boosting)
- **Evaluation Metrics**: MAE, MSE, R², cross-validation scores

### 3. Visualizer (`visualizations.py`)
- **Purpose**: Creates interactive charts and plots using Plotly
- **Visualization Types**:
  - Salary distribution histograms with statistical overlays
  - Correlation matrices for feature analysis
  - Interactive scatter plots and box plots

### 4. Utilities (`utils.py`)
- **Purpose**: Provides helper functions and sample data generation
- **Sample Data Features**:
  - Realistic employee demographics (age, experience, education)
  - Multiple departments with role hierarchies
  - Geographic location factors
  - Salary calculation based on multiple factors

### 5. Main Application (`app.py`)
- **Purpose**: Orchestrates the entire application flow
- **Page Structure**:
  - Data Upload & Analysis
  - Model Training
  - Salary Prediction
  - Model Comparison

## Data Flow

1. **Data Ingestion**: Users upload CSV files or generate sample data
2. **Data Analysis**: Exploratory data analysis with statistical summaries and visualizations
3. **Preprocessing**: Automated data cleaning, encoding, and scaling
4. **Model Training**: Multiple algorithms trained and evaluated with cross-validation
5. **Prediction**: Interactive salary prediction interface
6. **Comparison**: Side-by-side model performance analysis

## External Dependencies

### Core ML Libraries
- **scikit-learn**: Primary machine learning framework for preprocessing, models, and evaluation
- **XGBoost**: Advanced gradient boosting algorithm for improved predictions
- **pandas**: Data manipulation and analysis
- **numpy**: Numerical computing foundation

### Visualization and UI
- **Streamlit**: Web application framework and UI components
- **Plotly**: Interactive plotting library for charts and graphs
- **seaborn**: Statistical data visualization (imported but not extensively used)

### Data Processing
- **StandardScaler**: Feature normalization
- **OneHotEncoder**: Categorical variable encoding
- **ColumnTransformer**: Unified preprocessing pipeline

## Deployment Strategy

### Local Development
- **Environment**: Python-based with pip-installable dependencies
- **Execution**: `streamlit run app.py` for local development server
- **Port**: Default Streamlit port (8501) with auto-reload capabilities

### Session Management
- **State Persistence**: Streamlit session state maintains data and models across page navigation
- **Memory Management**: In-memory storage for datasets and trained models
- **User Experience**: Seamless navigation without data loss

### Scalability Considerations
- **Model Storage**: In-session model storage suitable for single-user applications
- **Data Handling**: Pandas-based processing suitable for moderate dataset sizes
- **Performance**: Optimized for interactive use with reasonable response times

## Architecture Benefits

1. **Modularity**: Clear separation allows for easy maintenance and testing
2. **Extensibility**: New models can be easily added to the ModelTrainer class
3. **User-Friendly**: Streamlit provides intuitive interface for non-technical users
4. **Comprehensive**: End-to-end solution from data upload to model comparison
5. **Interactive**: Real-time visualizations and immediate feedback

## Limitations and Considerations

1. **Scale**: Designed for moderate datasets (thousands of records)
2. **Persistence**: No database storage - data exists only during session
3. **Multi-user**: Single-user application without authentication
4. **Model Deployment**: No production ML model serving infrastructure
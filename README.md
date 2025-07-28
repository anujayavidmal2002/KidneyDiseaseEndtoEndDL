# Kidney Disease Classification - End-to-End Deep Learning Pipeline

An end-to-end deep learning pipeline for kidney disease classification from CT scan images using TensorFlow, with MLflow experiment tracking and DVC for reproducible ML workflows. Features automated data ingestion, model training with transfer learning, and comprehensive evaluation in a production-ready architecture.

## Overview

This project demonstrates a complete machine learning pipeline for medical image classification, specifically focusing on kidney disease detection from CT scan images. The system is built using modern MLOps practices, ensuring reproducibility, scalability, and maintainability.

## Features

- **Deep Learning Classification**: CNN-based image classification using TensorFlow and Keras
- **MLOps Integration**: Complete pipeline with DVC for version control and reproducibility  
- **Experiment Tracking**: MLflow integration with DagHub for model versioning and metrics logging
- **Transfer Learning**: Leverages pre-trained models for improved performance
- **Modular Architecture**: Well-structured codebase with separate configuration management
- **Automated Workflows**: End-to-end pipeline from data ingestion to model evaluation

## Technology Stack

- **Machine Learning**: TensorFlow, Keras
- **Experiment Tracking**: MLflow, DagHub
- **Pipeline Management**: DVC (Data Version Control)
- **Development Environment**: Python, Jupyter Notebooks
- **Configuration Management**: YAML-based configuration files

## Project Structure

```
KidneyDiseaseEndtoEndDL/
├── src/
│   └── cnnClassifier/
│       ├── components/          # Core ML components
│       ├── config/             # Configuration management
│       ├── constants/          # Project constants
│       ├── entity/            # Data classes and entities
│       ├── pipeline/          # Pipeline stages
│       └── utils/             # Utility functions
├── research/                   # Jupyter notebooks for experimentation
├── artifacts/                  # Generated artifacts and models
├── config/                    # Configuration files
├── dvc.yaml                   # DVC pipeline definition
└── params.yaml               # Model parameters
```

## Pipeline Stages

### 1. Data Ingestion
- Downloads and extracts CT scan image datasets
- Organizes data into proper directory structure
- Validates data integrity

### 2. Base Model Preparation  
- Configures pre-trained CNN models
- Sets up transfer learning architecture
- Prepares model for fine-tuning

### 3. Model Training
- Implements data augmentation techniques
- Fine-tunes pre-trained models on kidney disease data
- Saves trained model artifacts

### 4. Model Evaluation
- Evaluates model performance on validation data
- Logs metrics and parameters to MLflow
- Generates comprehensive evaluation reports

## Getting Started

### Prerequisites
- Python 3.8+
- Git
- DVC

### Installation

1. Clone the repository:
```bash
git clone https://github.com/anujayavidmal2002/KidneyDiseaseEndtoEndDL.git
cd KidneyDiseaseEndtoEndDL
```

2. Create and activate virtual environment:
```bash
python -m venv kidney
kidney\Scripts\activate  # On Windows
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Configure MLflow tracking (optional):
```bash
# Set your DagHub credentials
export MLFLOW_TRACKING_URI="https://dagshub.com/your-username/KidneyDiseaseEndtoEndDL.mlflow"
export MLFLOW_TRACKING_USERNAME="your-username"  
export MLFLOW_TRACKING_PASSWORD="your-token"
```

### Running the Pipeline

Execute the complete pipeline using DVC:
```bash
dvc repro
```

Or run individual stages:
```bash
python src/cnnClassifier/pipeline/stage_01_data_ingestion.py
python src/cnnClassifier/pipeline/stage_02_prepare_base_model.py
python src/cnnClassifier/pipeline/stage_03_model_training.py
python src/cnnClassifier/pipeline/stage_04_model_evaluation.py
```

## Configuration

The project uses YAML-based configuration management:

- `config/config.yaml`: Main configuration file
- `params.yaml`: Model hyperparameters and training settings
- `dvc.yaml`: Pipeline stage definitions

## Experiment Tracking

All experiments are tracked using MLflow and can be viewed on DagHub. The system logs:
- Model parameters and hyperparameters
- Training and validation metrics
- Model artifacts and versions

## Model Performance

The model uses transfer learning with pre-trained CNN architectures to achieve optimal performance on kidney disease classification tasks. Detailed performance metrics are available in the MLflow tracking interface.

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-feature`)
3. Commit changes (`git commit -am 'Add new feature'`)
4. Push to branch (`git push origin feature/new-feature`)
5. Create a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- Medical imaging datasets used for training
- TensorFlow and Keras communities
- MLflow and DVC development

# Pneumonia Detection from Chest X-ray Images

## Overview

Pneumonia is a serious respiratory infection that primarily affects the lungs and can be life-threatening if not diagnosed and treated promptly. Missing a pneumonia diagnosis can lead to severe complications, prolonged illness, and even death, particularly in vulnerable populations such as the elderly and young children. Traditional methods of diagnosing pneumonia involve the manual inspection of chest X-rays by radiologists, which can be time-consuming and prone to human error. This project aims to develop a machine learning model to automatically classify chest X-ray images as either normal or pneumonia, providing a tool that can assist radiologists in making faster and more accurate diagnoses. This tool aims to reduce the risk of missed diagnoses and improve patient outcomes by ensuring timely and precise detection of pneumonia cases.


## Data Source

The dataset used in this project is from [Kaggle](https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia/data). The dataset contains chest X-ray images categorized into two classes: normal and pneumonia. The images were selected from retrospective cohorts of pediatric patients of one to five years old from Guangzhou Women and Children’s Medical Center. All chest X-ray imaging was performed as part of patients’ routine clinical care, ensuring the dataset's suitability for this project as it closely resembles real-world clinical scenarios.


## Stakeholders

The primary stakeholders for this project include:

- **Radiologists and Medical Practitioners**: who can use the tool to assist in diagnosing pneumonia more quickly and accurately.
- **Hospitals and Clinics**: which can integrate this model into their diagnostic systems to improve efficiency and patient outcomes.
- **Patients**: who benefit from quicker diagnoses and treatment, potentially reducing the severity and duration of the illness.


## Summary of Data Science Steps

1. **Data Preparation**: 
   - Loaded and rescaled the chest X-ray images.
   - Created training, validation, and test data generators.
   - Checked class distributions to ensure balanced validation data.

2. **Model Iteration Process**:
   - Started with a baseline neural network.
   - Experimented with L1 and L2 regularization to prevent overfitting.
   - Applied dropout layers to improve model generalization.
   - Transitioned to a Convolutional Neural Network (CNN) to better capture spatial features.
   - Implemented class balancing to address dataset imbalance.
   - Added more layers to the CNN to increase its capacity.
   - Combined class balancing with dropout for the best performance.

3. **Model Evaluation**:
   - Evaluated each model on validation data.
   - Selected the best-performing model based on validation metrics.
   - Tested the final model on holdout test data.

## Model Performance on Evaluation Data

The final model's performance on the test data is as follows:

- **Test Loss**: 0.5691
- **Test Accuracy**: 0.7837
- **Precision**: 0.6311
- **Recall**: 0.8333
- **F1 Score**: 0.7182

These results indicate that the model correctly classifies chest X-ray images 78.37% of the time. The precision of 0.6311 means that when the model predicts pneumonia, it is correct 63.11% of the time, which is critical for reducing unnecessary treatments. The recall of 0.8333 indicates that the model successfully identifies 83.33% of all actual pneumonia cases, which is crucial for ensuring that most cases are detected and treated promptly. The F1 score of 0.7182 reflects a balanced trade-off between precision and recall, ensuring a reliable overall performance. Out of 390 actual pneumonia cases, the model correctly identified 325, and out of 234 normal cases, the model correctly identified 44.


## Justification of Metrics and Chosen Model

Precision and recall are particularly important in the context of pneumonia detection. High recall (83.33%) ensures that most pneumonia cases are detected, which is crucial for timely treatment and reducing the risk of severe complications or death. High precision (63.11%) minimizes the number of false positives, reducing unnecessary costly testing and treatment. The chosen model balances these metrics, resulting in an F1 score of 0.7182, which indicates a good overall performance. The implications of these metrics are significant for both patient outcomes and healthcare efficiency.


## Implications for Stakeholders

- **Radiologists and Medical Practitioners**: The model serves as a valuable tool for aiding in the diagnosis of pneumonia, potentially reducing the workload and human error.
- **Hospitals and Clinics**: Integrating this model can enhance diagnostic processes, improve patient throughput, and ensure timely and accurate diagnoses.
- **Patients**: Quicker and more accurate diagnoses lead to faster treatment, better outcomes, and reduced risk of complications.


## Repository Structure



## Reproducibility Script
This section provides instructions to reproduce the results of this project. Follow the steps below to set up the environment, download the data, and run the code.

### Step 1: Environment Setup

1. **Clone the Repository**
   ```bash
   git clone [https://github.com/agambino720/pneumonia_identification_model]
   cd pneumonia_identification_model

2. **Create a Virtual Environment**
   ```bash
   python -m venv env source env/bin/activate

4. **Install Required Packages**
   ```bash
   pip install -r requirements.txt

### Step 2: Data Download

1. **Create the Data Directory**
   ```bash
   mkdir -p data

2. **Download the Dataset**
  - Download the dataset from this link: https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia/data
  - Extract the dataset and place it in the data/ directory

3. **Extract the Dataset**
  ```bash
   unzip data/archive.zip -d data/  
```
After extraction, ensure the dataset directory structure looks like this:

data/
├── archive/
    ├── chest_xray/
        ├── train/
        ├── val/
        └── test/

### Step 3: Preprocess the Data

1. **Preprocess the Data**
   
Run the following command to preprocess the data:
```bash
jupyter nbconvert --to notebook --execute preprocess_data.py.ipynb
```

### Step 4: Model Training and Validation

1. **Train and Validate the Model**
   
Run the following command to train and validate the model:
```bash
jupyter nbconvert --to notebook --execute train_val_model.py.ipynb
```

### Step 5: Model Evaluation

1. **Evaluate the Model**
   
Run the following command to evaluate the model:
```bash
jupyter nbconvert --to notebook --execute evaluate_model.py.ipynb
```

This script includes all the necessary steps to set up the environment, download and extract the data, preprocess the data, train and validate the model, and evaluate the model.

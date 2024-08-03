# pneumonia_identification_model

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

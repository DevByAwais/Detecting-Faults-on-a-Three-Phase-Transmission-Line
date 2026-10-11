
# Detecting Faults on a Three-Phase Transmission Line

## Overview

This project focuses on detecting electrical faults in a three-phase transmission line using machine learning. The model uses three-phase current and voltage measurements to classify each observation as either a fault or a no-fault condition.

The project compares Logistic Regression implemented from scratch with Linear SVM and RBF Kernel SVM models.

## Objectives

- Load and prepare the electrical fault detection dataset.
- Perform exploratory data analysis and visualize current measurements.
- Implement Logistic Regression using NumPy and batch gradient descent.
- Compare raw features with squared features.
- Train Linear and RBF Kernel Support Vector Machines.
- Evaluate models using accuracy, confusion matrices, missed faults, and false alarms.
- Develop a simple web interface for comparing predictions.

## Dataset

Dataset: Electrical Fault Detection and Classification

Source: https://www.kaggle.com/datasets/esathyaprakash/electrical-fault-detection-and-classification

Required file: `detect dataset.csv`

Place the downloaded dataset in the `data/` directory.

The input features are:

- `Ia`, `Ib`, `Ic`: Three-phase line currents.
- `Va`, `Vb`, `Vc`: Three-phase line voltages.

The target label is:

- `fault = 1`: Fault detected.
- `fault = 0`: No fault detected.

## Models

### 1. Logistic Regression

Implemented from scratch using NumPy, including:

- Sigmoid function
- Hypothesis function
- Cost function
- Batch gradient descent
- Binary prediction

Two feature sets are compared:

- **Set R:** Six raw current and voltage features.
- **Set Q:** Six raw features and their six squared features.

### 2. Support Vector Machines

SVM models are trained using `sklearn.svm.SVC`.

- Linear SVM
- RBF Kernel SVM

Hyperparameters are selected using validation accuracy.

## Evaluation Metrics

The models are evaluated using:

- Accuracy
- Confusion matrix
- Missed faults
- False alarms
- Number of support vectors for SVM models

Missed faults are especially important because a missed fault could prevent a protective relay from responding to an electrical fault.

## Project Structure

```text
.
├── data/
│   └── detect dataset.csv
├── src/
│   ├── load_data.py
│   ├── prepare.py
│   ├── eda.py
│   ├── logistic.py
│   ├── metrics.py
│   ├── train_logistic.py
│   ├── train_svm.py
│   └── test_models.py
├── results/
│   ├── analysis.md
│   ├── figures/
│   └── models/
├── app/
├── requirements.txt
└── README.md
```

## Installation

Python 3.10 or a compatible Python version is recommended.

Clone the repository:

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
cd YOUR_REPOSITORY_NAME
```

Create and activate a virtual environment if required.

Install dependencies:

```bash
pip install -r requirements.txt
```

Alternatively:

```bash
pip install numpy pandas matplotlib scikit-learn joblib streamlit
```

## How to Run

Run the following scripts in the order supported by your implementation:

```bash
python src/load_data.py
python src/prepare.py
python src/eda.py
python src/train_logistic.py
python src/train_svm.py
python src/test_models.py
```

Run the web interface:

```bash
streamlit run app/app.py
```

Enter the six current and voltage measurements to view predictions from the saved Set-Q Logistic Regression and RBF SVM models.

## Results

Add your actual results after running the experiments.

| Model | Test Accuracy | Missed Faults | False Alarms |
|---|---|---|---|
| Logistic Regression - Set R | To be added | To be added | To be added |
| Logistic Regression - Set Q | To be added | To be added | To be added |
| Linear SVM | To be added | To be added | To be added |
| RBF SVM | To be added | To be added | To be added |

## Web Interface

Add a screenshot of your working web interface here.

Example Markdown syntax:

```markdown
![Fault Detection Web Interface](results/figures/interface.png)
```

## Analysis

The project investigates whether adding squared features improves Logistic Regression performance and whether an RBF kernel can classify electrical faults more effectively than a linear decision boundary.

The final discussion should compare model accuracy, missed faults, false alarms, and support vectors. The model selection should consider the safety requirements of fault detection rather than accuracy alone.

## Medium Blog

[Add your published Medium blog URL here]

## Team Members

- Member 1: Your Name
- Member 2: Teammate's Name

## Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- Scikit-learn SVC
- Joblib
- Streamlit

## License

This repository was developed for academic purposes as part of the AI4003 Applied Machine Learning course.

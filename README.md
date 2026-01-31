# Fraud Detection in Financial Transactions

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

## Overview

This project implements a machine learning-based fraud detection system for financial transactions. The solution addresses the critical challenge of identifying fraudulent activities within large volumes of legitimate transactions, which are typically rare and difficult to detect. By leveraging advanced data analysis and predictive modeling techniques, this system provides actionable insights to prevent financial losses and enhance security.

The analysis follows a comprehensive end-to-end data science workflow, including exploratory data analysis, feature engineering, model development, and performance evaluation. Special emphasis is placed on handling severe class imbalance and translating technical findings into practical fraud prevention strategies suitable for real-world deployment.

## Table of Contents

- [Features](#features)
- [Dataset](#dataset)
- [Installation](#installation)
- [Usage](#usage)
- [Dependencies](#dependencies)
- [Model Architecture](#model-architecture)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Features

- **Comprehensive EDA**: In-depth analysis of transaction patterns, fraud distribution, and correlations
- **Advanced Feature Engineering**: Creation of balance differences and other engineered features
- **Class Imbalance Handling**: Implementation of class weighting and stratified sampling
- **Random Forest Model**: Robust ensemble learning approach for fraud detection
- **Performance Evaluation**: Detailed metrics including ROC-AUC, confusion matrix, and feature importance
- **Business Insights**: Translation of model outputs into actionable fraud prevention strategies
- **Monitoring Framework**: Guidelines for ongoing effectiveness measurement

## Dataset

The dataset used in this project simulates financial transactions over a 30-day period. It contains the following key features:

- **step**: Unit of time (1 hour increments, total 744 steps)
- **type**: Transaction type (CASH-IN, CASH-OUT, DEBIT, PAYMENT, TRANSFER)
- **amount**: Transaction amount in local currency
- **nameOrig**: Customer initiating the transaction
- **oldbalanceOrg**: Initial balance before transaction
- **newbalanceOrig**: New balance after transaction
- **nameDest**: Recipient customer
- **oldbalanceDest**: Recipient's initial balance
- **newbalanceDest**: Recipient's new balance
- **isFraud**: Target variable (1 for fraudulent, 0 for legitimate)
- **isFlaggedFraud**: Business rule flag for large transfers (>200,000)

**Note**: Balance information is not available for merchant accounts (starting with 'M').

The dataset exhibits severe class imbalance, with fraudulent transactions representing less than 1% of all transactions.

## Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/fraud-detection.git
   cd fraud-detection
   ```

2. **Set up Python environment**:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Launch Jupyter Notebook**:
   ```bash
   jupyter notebook
   ```

## Usage

1. Open `Fraud_Detection.ipynb` in Jupyter Notebook
2. Execute cells sequentially to run the complete analysis
3. The notebook is self-contained and includes:
   - Data loading and preprocessing
   - Exploratory data analysis
   - Feature engineering
   - Model training and evaluation
   - Results interpretation and recommendations

### Key Outputs

- Fraud detection model with performance metrics
- Feature importance analysis
- Fraud prevention strategy recommendations
- Monitoring framework for ongoing evaluation

## Dependencies

- Python 3.8+
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn

See `requirements.txt` for exact versions.

## Model Architecture

### Random Forest Classifier

- **Algorithm**: Ensemble learning with multiple decision trees
- **Class Imbalance Handling**: Class weighting based on inverse frequency
- **Hyperparameter Tuning**: Randomized search cross-validation
- **Evaluation Metrics**:
  - ROC-AUC Score
  - Precision, Recall, F1-Score
  - Confusion Matrix
  - Feature Importance

### Key Hyperparameters

- n_estimators: Optimized through cross-validation
- max_depth: Tuned to prevent overfitting
- class_weight: 'balanced' for handling imbalance

## Results

### Model Performance

- **ROC-AUC**: [Insert value from notebook]
- **Precision on Fraud Class**: [Insert value]
- **Recall on Fraud Class**: [Insert value]
- **F1-Score**: [Insert value]

### Key Insights

1. **Transaction Types**: TRANSFER and CASH_OUT are most associated with fraud
2. **Amount Patterns**: Fraudulent transactions often involve large amounts
3. **Balance Behavior**: Unusual balance changes are strong indicators
4. **Merchant Accounts**: Transactions involving merchants show different patterns

### Business Impact

- Potential to reduce financial losses through early fraud detection
- Improved customer trust through enhanced security measures
- Operational efficiency through automated monitoring

## Contributing

We welcome contributions to improve this fraud detection system. Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Development Guidelines

- Follow PEP 8 style guidelines
- Add docstrings to new functions
- Include unit tests for new features
- Update documentation as needed

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact

For questions or collaborations:

- **Project Lead**: [Your Name]
- **Email**: [your.email@example.com]
- **LinkedIn**: [Your LinkedIn Profile]
- **GitHub**: [@your-username](https://github.com/your-username)

---

**Disclaimer**: This project is for educational and research purposes. Always consult with financial experts and legal advisors before implementing fraud detection systems in production environments.
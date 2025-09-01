# FinSafe: AI Driven Credit Scoring

FinSafe is an intelligent credit scoring application that leverages machine learning to assess the creditworthiness of loan applicants. The application provides real-time credit score calculations, default probability assessments, and risk ratings through an intuitive web interface.

## Features

- **Real-time Credit Assessment**: Instantly calculate credit scores and default probabilities
- **Comprehensive Risk Analysis**: Evaluates multiple financial and demographic factors
- **User-friendly Interface**: Clean, intuitive Streamlit-based web application
- **Multiple Loan Types**: Supports various loan purposes (Education, Home, Auto, Personal)
- **Credit Rating System**: Provides clear ratings from Poor to Excellent (300-900 scale)

## How It Works

The application uses a trained machine learning model to analyze:

- **Personal Information**: Age, income, residence type
- **Loan Details**: Amount, tenure, purpose, type (secured/unsecured)
- **Credit History**: Delinquency ratio, average days past due, credit utilization
- **Account Information**: Number of open loan accounts

Based on these inputs, FinSafe calculates:
- **Default Probability**: Likelihood of loan default (as percentage)
- **Credit Score**: Numerical score between 300-900
- **Credit Rating**: Categorical rating (Poor/Average/Good/Excellent)

## Installation

### Prerequisites

- Python 3.7 or higher
- pip package manager

### Setup

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/ml_project_CRM.git
   cd ml_project_CRM
   ```

2. **Create a virtual environment** (recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Ensure model artifacts are available**:
   Make sure the `artifacts/model_data.joblib` file is present in your project directory. This file contains the trained model, scaler, and feature information.

## Usage

1. **Run the application**:
   ```bash
   streamlit run main.py
   ```

2. **Open your browser** and navigate to `http://localhost:8501`

3. **Input the required information**:
   - Age (18-100)
   - Income
   - Loan amount
   - Loan tenure in months
   - Average days past due (DPD)
   - Delinquency ratio (0-100%)
   - Credit utilization ratio (0-100%)
   - Number of open loan accounts (1-4)
   - Residence type (Owned/Rented/Mortgage)
   - Loan purpose (Education/Home/Auto/Personal)
   - Loan type (Secured/Unsecured)

4. **Click "Calculate Risk"** to get your results

## Project Structure

```
ml_project_CRM/
├── main.py                 # Main Streamlit application
├── prediction_helper.py    # Model prediction and data processing logic
├── requirements.txt        # Python dependencies
├── .gitignore             # Git ignore file
├── README.md              # Project documentation
└── artifacts/             # Model artifacts (not in repository)
    └── model_data.joblib  # Trained model, scaler, and features
```

## File Descriptions

- **`main.py`**: The main Streamlit application that provides the user interface for input collection and result display
- **`prediction_helper.py`**: Contains the core prediction logic, data preprocessing, and credit score calculation functions
- **`requirements.txt`**: Lists all Python package dependencies needed to run the application

## Credit Score Scale

- **300-499**: Poor - High risk applicant
- **500-649**: Average - Moderate risk applicant  
- **650-749**: Good - Low risk applicant
- **750-900**: Excellent - Very low risk applicant

## Technical Details

### Model Features

The model uses the following features for prediction:
- Age and demographic information
- Loan-to-income ratio (automatically calculated)
- Credit utilization and delinquency metrics
- Account history and behavior patterns
- Loan characteristics (type, purpose, tenure)

### Machine Learning Pipeline

1. **Data Preprocessing**: Input validation and feature engineering
2. **Scaling**: MinMax scaling applied to numerical features
3. **Prediction**: Logistic regression model generates probability scores
4. **Score Transformation**: Probabilities converted to 300-900 credit score scale

## Dependencies

- **streamlit**: Web application framework
- **joblib**: Model serialization and loading
- **numpy**: Numerical computations
- **pandas**: Data manipulation and analysis
- **scikit-learn**: Machine learning model and preprocessing tools

## Development

To contribute to this project:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Make your changes
4. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
5. Push to the branch (`git push origin feature/AmazingFeature`)
6. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

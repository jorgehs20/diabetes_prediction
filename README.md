# 🏥 Diabetes Prediction with Amazon SageMaker

A machine learning project for predicting diabetes onset using clinical data processed from FHIR healthcare records stored in AWS HealthLake.

## 📋 Project Overview

This project demonstrates a complete ML workflow for healthcare data, from exploratory data analysis to model deployment using Amazon SageMaker. The dataset contains clinical features processed by a Data Science team through Amazon DataZone.

## 🎯 Learning Objectives

- Understand healthcare ML workflows with imbalanced data
- Perform exploratory data analysis on clinical features
- Train baseline models locally using scikit-learn
- Scale training using Amazon SageMaker Training Jobs
- Deploy models to SageMaker endpoints for real-time predictions
- Compare local vs SageMaker training approaches

## 📊 Dataset Features

| Feature | Description | Clinical Significance |
|---------|-------------|----------------------|
| `Glucose` | Blood glucose level (mg/dL) | Fasting glucose ≥ 126 mg/dL indicates diabetes |
| `Hemoglobin A1c` | HbA1c percentage | HbA1c ≥ 6.5% indicates diabetes |
| `Body Mass Index` | BMI (kg/m²) | Risk factor for diabetes |
| `Body Weight` | Weight in kg | Related to diabetes risk |
| `label_diabetes_onset` | Target variable | 0=No diabetes, 1=Diabetes |

## 🚀 Getting Started

### Prerequisites

- AWS Account with SageMaker access
- Python 3.8+
- Jupyter Notebook environment

### Required Libraries

```bash
pip install pandas numpy matplotlib seaborn boto3 sagemaker scikit-learn
```

### Running the Notebook

1. Clone this repository
2. Open `diabetes_prediction.ipynb` in your Jupyter environment
3. Ensure you have AWS credentials configured
4. Run cells sequentially

## 📈 Model Performance

The project addresses severe class imbalance (~1.2% diabetes cases) using:
- Stratified sampling techniques
- Appropriate evaluation metrics (F1-score, AUC-ROC)
- Clinical context-aware feature engineering

## 🏗️ Architecture

```
Data Source (AWS HealthLake) 
    ↓
Data Processing (AWS Glue)
    ↓
Data Catalog (Amazon DataZone)
    ↓
ML Training (Amazon SageMaker)
    ↓
Model Deployment (SageMaker Endpoints)
```

## 📁 Project Structure

```
├── diabetes_prediction.ipynb    # Main notebook with complete ML workflow
└── README.md                   # Project documentation
```

## 🔧 Key Technologies

- **Amazon SageMaker**: ML training and deployment platform
- **AWS HealthLake**: FHIR-compliant healthcare data storage
- **Amazon DataZone**: Data governance and discovery
- **scikit-learn**: Machine learning algorithms
- **Pandas/NumPy**: Data manipulation and analysis

## 📝 Clinical Context

This project uses real-world clinical thresholds:
- **Diabetes diagnosis**: HbA1c ≥ 6.5% OR fasting glucose ≥ 126 mg/dL
- **Pre-diabetes**: HbA1c 5.7-6.4% OR fasting glucose 100-125 mg/dL
- **Normal**: HbA1c < 5.7% AND fasting glucose < 100 mg/dL

## ⚠️ Important Notes

- This is for educational purposes only
- Not intended for actual clinical diagnosis
- Always consult healthcare professionals for medical decisions
- Ensure HIPAA compliance when working with real healthcare data

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🆘 Support

For questions or issues:
- Open an issue in this repository
- Check AWS SageMaker documentation
- Review scikit-learn documentation for ML algorithms

---

**Duration**: ~30 minutes  
**Difficulty**: Intermediate  
**Domain**: Healthcare ML, AWS SageMaker
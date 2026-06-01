# Conversion Insight: Bank Marketing Success Factor Analysis

## Project Overview
This project analyzes a bank marketing dataset to identify key factors that contribute to successful customer conversions (subscription to a term deposit). Using decision tree modeling, the analysis determines which features have the greatest predictive power in determining conversion success.

## Dataset
The dataset contains information about direct marketing campaigns (phone calls) of a Portuguese banking institution. The classification goal is to predict if a client will subscribe to a term deposit (target variable 'y').

### Data Source
The dataset is available from the UCI Machine Learning Repository:
- Source: [Bank Marketing Dataset](https://raw.githubusercontent.com/rajeevratan84/datascienceforbusiness/master/bank-full.csv)

### Data Features
The dataset includes various bank client attributes, campaign details, and economic indicators:

| Feature | Type | Description |
|---------|------|-------------|
| age | numeric | Client's age |
| job | categorical | Client's occupation type |
| marital | categorical | Marital status |
| education | categorical | Education level |
| default | categorical | Has credit in default? |
| balance | numeric | Average yearly balance in euros |
| housing | categorical | Has housing loan? |
| loan | categorical | Has personal loan? |
| contact | categorical | Contact communication type |
| day | numeric | Last contact day of the month |
| month | categorical | Last contact month of the year |
| duration | numeric | Last contact duration in seconds |
| campaign | numeric | Number of contacts during this campaign |
| pdays | numeric | Days since last contact from previous campaign |
| previous | numeric | Number of contacts before this campaign |
| poutcome | categorical | Outcome of previous marketing campaign |
| converted | binary | Target variable - did client subscribe? (0=no, 1=yes) |

## Methodology
1. **Data Preparation**:
   - Loaded and inspected the dataset
   - Transformed categorical values into dummy variables
   - Converted binary text values to numeric (yes/no → 1/0)
   - Ensured all features were properly encoded for modeling

2. **Model Development**:
   - Used a Decision Tree Classifier with max depth of 5 to prevent overfitting
   - Split data into 80% training and 20% testing sets
   - Implemented permutation-based feature importance analysis

3. **Model Evaluation**:
   - Achieved 89.62% accuracy on the test dataset
   - Generated a classification report with precision, recall, and F1-score
   - Calculated confusion matrix and AUC-ROC score

## Key Findings
The most significant predictors of conversion success are:

1. **Call duration** (duration) - By far the most important factor
2. **Previous success** (poutcome_success) - Second most important factor
3. **Client age** (age) - Third most important factor
4. **Account balance** (balance) - Fourth most important factor
5. **Contact month** (month) - Fifth most important factor

The model achieved an AUC-ROC score of 0.86, indicating strong discriminative ability for identifying potential customers.

## Model Performance
- **Accuracy**: 89.62%
- **Precision** (for positive class): 0.31
- **Recall** (for positive class): 0.64
- **F1-score** (for positive class): 0.42
- **AUC-ROC Score**: 0.86

## Requirements
```
pandas
numpy
scikit-learn
matplotlib
seaborn
```

## Usage
The notebook contains a complete workflow from data loading to model evaluation:
1. Load and preprocess the bank marketing dataset
2. Convert categorical variables to numeric
3. Train a decision tree classifier
4. Analyze feature importance
5. Evaluate model performance

## Conclusion
This analysis reveals that the duration of the last contact call is overwhelmingly the most significant predictor of conversion success. Previous campaign success and client age also play important roles. These insights can help banking institutions optimize their marketing strategies by focusing on promising leads and potentially adjusting call strategies to increase engagement time with potential customers.

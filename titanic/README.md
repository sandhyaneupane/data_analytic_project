# Titanic Survival Prediction Project

## Overview

This project implements a machine learning solution to predict passenger survival on the Titanic using the famous Kaggle Titanic dataset. The project uses logistic regression to classify passengers as either survivors (1) or non-survivors (0) based on various passenger characteristics.

## Project Structure

```
titanic/
├── README.md                 # This file
├── codejup-1.ipynb          # Main Jupyter notebook with analysis and model
└── submission.csv           # Final predictions for test dataset
```

## Dataset Description

The Titanic dataset contains information about passengers aboard the RMS Titanic, including:

- **PassengerId**: Unique identifier for each passenger
- **Survived**: Target variable (0 = did not survive, 1 = survived)
- **Pclass**: Ticket class (1st, 2nd, 3rd class)
- **Name**: Passenger name
- **Sex**: Gender (male/female)
- **Age**: Age in years
- **SibSp**: Number of siblings/spouses aboard
- **Parch**: Number of parents/children aboard
- **Ticket**: Ticket number
- **Fare**: Ticket fare
- **Cabin**: Cabin number
- **Embarked**: Port of embarkation (C, Q, S)

## Methodology

### 1. Data Preprocessing

The project implements a comprehensive data cleaning pipeline:

- **Feature Selection**: Removed unnecessary columns (`Ticket`, `Cabin`, `Name`, `PassengerId`)
- **Missing Value Handling**: 
  - Filled missing age values with median age
  - Filled missing fare values with median fare
  - Filled missing embarked values with 'U' (Unknown)
- **Categorical Encoding**: Used LabelEncoder to convert categorical variables (`Sex`, `Embarked`) to numeric format

### 2. Model Selection and Training

- **Algorithm**: Logistic Regression
- **Rationale**: Binary classification problem (survival prediction) makes logistic regression an appropriate choice
- **Training Setup**: 
  - Split training data into 80% training and 20% validation sets
  - Used random state for reproducibility
  - Set maximum iterations to 1000 for convergence

### 3. Model Evaluation

The model was evaluated using accuracy score on the validation set to assess performance before making final predictions.

## Key Features Used

After preprocessing, the model uses the following features:
- `Pclass`: Passenger class
- `Sex`: Gender (encoded as numeric)
- `Age`: Age in years
- `SibSp`: Number of siblings/spouses
- `Parch`: Number of parents/children
- `Fare`: Ticket fare
- `Embarked`: Port of embarkation (encoded as numeric)

## Results

The final predictions are saved in `submission.csv` with the following format:
- `PassengerId`: Passenger identifier from test dataset
- `Survived`: Predicted survival status (0 or 1)

The submission file contains predictions for 418 test passengers (PassengerId 892-1309).

## Usage

### Running the Analysis

1. **Prerequisites**: Ensure you have the required Python packages:
   ```bash
   pip install pandas scikit-learn jupyter
   ```

2. **Data**: Place the Titanic dataset files (`train.csv`, `test.csv`) in the project directory

3. **Execution**: Open and run the `codejup-1.ipynb` notebook:
   ```bash
   jupyter notebook codejup-1.ipynb
   ```

### Output

The notebook will generate:
- Data exploration and analysis
- Model training and validation
- Final predictions saved to `submission.csv`

## Technical Details

### Data Cleaning Function

The project includes a custom `clean()` function that:
- Removes unnecessary columns
- Handles missing values using median imputation
- Maintains data consistency between training and test sets

### Model Configuration

```python
model = LogisticRegression(random_state=0, max_iter=1000)
```

### Validation Strategy

- 80/20 train-validation split
- Random state set to 42 for reproducibility
- Accuracy score used for model evaluation

## Future Improvements

Potential enhancements to consider:
1. **Feature Engineering**: Create new features from existing ones (e.g., family size, title extraction)
2. **Advanced Models**: Try ensemble methods (Random Forest, Gradient Boosting)
3. **Hyperparameter Tuning**: Optimize model parameters using cross-validation
4. **Missing Value Strategies**: Implement more sophisticated imputation methods
5. **Feature Selection**: Use techniques to identify most important features

## Dependencies

- pandas
- scikit-learn
- jupyter (for notebook execution)

## License

This project is for educational purposes and follows standard data science practices for the Titanic survival prediction challenge.

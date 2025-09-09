# Titanic Survival Analysis

## 🚢 Problem Statement
The Titanic dataset is a classic machine learning challenge:  
Can we predict which passengers survived the Titanic disaster based on their personal and travel information?

Dataset source: [Kaggle Titanic Competition](https://www.kaggle.com/c/titanic/data)

---

## 🔍 Process
1. **Data Cleaning**  
   - Handled missing values (Age, Cabin, Embarked).  
   - Converted categorical variables into numerical (e.g., Sex, Embarked).  

2. **Exploratory Data Analysis (EDA)**  
   - Visualized survival rates by gender, passenger class, age, and family size.  
   - Found strong correlations between class, gender, and survival.  

3. **Feature Engineering**  
   - Created new features like `FamilySize` and `IsAlone`.  
   - Binned Age and Fare into categories.  

4. **Modeling**  
   - Tested baseline models (Logistic Regression, Decision Tree, Random Forest).  
   - Compared accuracy using cross-validation.  

---

## 📊 Insights
- Women and children had significantly higher survival rates.  
- 1st-class passengers were more likely to survive than 3rd-class passengers.  
- Larger families tended to have lower survival chances compared to small families.  
- Random Forest performed better than Logistic Regression in prediction accuracy.  

---

## 📈 Visuals
Here are some example plots from the analysis:

- **Survival by Gender**  
  ![Survival by Gender](images/survival_by_gender.png)

- **Survival by Passenger Class**  
  ![Survival by Class](images/survival_by_class.png)

*(You can drag and drop screenshots of your graphs directly into this README on GitHub — GitHub will generate the correct image link automatically.)*

---

## 📌 Next Steps
- Try advanced models like XGBoost or LightGBM.  
- Perform hyperparameter tuning for better accuracy.  
- Explore ensemble methods.  

# **Customer-Response-Prediction-Wallace-Communications**

## Project Overview
Wallace Communications, a UK-based telecom company, aims to expand into the mobile telecom market by targeting existing landline customers with marketing campaigns. However, due to high call centre costs, the company wants to identify customers most likely to accept a new contract and avoid unnecessary outreach. This project develops and evaluates machine learning models to predict whether a customer will subscribe to a new mobile contract (new_contract_this_campaign).

## **Objectives**
- Build predictive models to classify customer responses
- Compare performance of:
  - Logistic Regression
  - Decision Tree
  - Neural Network
- Handle class imbalance effectively
- Optimise models using hyperparameter tuning
- Evaluate models using appropriate classification metrics

## **Dataset**
- Source: wallacecommunications.csv
- Size: 50,000+ customer records
- Target variable:
  - new_contract_this_campaign (Yes/No → converted to 1/0)
The dataset includes:
- Demographic data (e.g. age, marital status)
- Campaign interaction history
- Customer behaviour indicators

## **Methodology**
### **1. Exploratory Data Analysis (EDA)**
- Visualised distributions of numerical and categorical variables
- Identified:
  - Class imbalance in target variable
  - Patterns in customer behaviour
- Used histograms and bar charts for feature understanding

### **2. Data Cleaning & Preprocessing**
- Filtered dataset to UK customers only
- Removed invalid entries (e.g. unknown month values)
- Renamed and standardised categorical variables
- Dropped irrelevant columns (IDs, location fields, etc.)Converted target variable into binary format

### **3. Post-cleaning EDA**
Confirmed that:
- Invalid or inconsistent values had been successfully removed
- Categorical variables were standardised
- Feature distributions were logical and interpretable
- The dataset was suitable for modelling

### **4. Feature Engineering**
- Separated features (X) and target (y)
- Identified categorical vs numerical features
- Applied:
  - Label Encoding (for tree & neural network models)
  - One-Hot Encoding (for logistic regression)

### **5. Data Splitting**
- Train: 60%
- Validation: 20%
- Test: 20%
- Stratified sampling to preserve class distribution

### **6. Handling Class Imbalance**
- Applied SMOTE (Synthetic Minority Oversampling Technique) on training data
- Ensured balanced class representation for model training

### **7. Feature Scaling**
- Standardised numerical features using StandardScaler
- Applied only where appropriate:
  - Required for Logistic Regression and Neural Networks
  - Optional for Decision Trees

## **Models Implemented**
### **1. Logistic Regression**
- Baseline linear model
- Applied One-Hot Encoding + scaling
- Tuned using RandomizedSearchCV

### **2. Decision Tree**
- Non-linear model capturing complex patterns
- Used class_weight="balanced"
- Hyperparameters tuned:
  - max_depth
  - min_samples_split
  - min_samples_leaf
 
### **2. Neural Network (MLPClassifier)**
- Multi-layer perceptron with hidden layers
- Tuned:
  - hidden layer sizes
  - activation functions
  - learning rate
  - regularisation (alpha)
- Used early stopping to prevent overfitting

### **3. Neural Network (MLPClassifier)**
- Multi-layer perceptron with hidden layers
- Tuned:
  - hidden layer sizes
  - activation functions
  - learning rate
  - regularisation (alpha)
- Used early stopping to prevent overfitting

## **Model Evaluation**
### **Metrics Used:**
- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix
- F1-score was prioritised due to class imbalance and business need to balance precision and recall.

## **Results Summary**
- All models were evaluated on validation and test sets
- Performance compared across key metrics
- Confusion matrices used to visualise prediction accuracy

## **Key Insights:**
- Decision Tree provided strong interpretability
- Neural Network captured more complex patterns
- Logistic Regression offered a solid baseline

## **Feature Importance**
- Extracted from Decision Tree model
- Top features influencing predictions were visualised
- Provided business insight into:
  - Customer behaviour
  - Campaign effectiveness
 
## **Key Learnings**
- Handling class imbalance is critical in marketing prediction tasks
- Combining data analysis + business understanding improves model relevance
- Model interpretability (e.g. Decision Trees) is valuable for stakeholders
- Different models offer trade-offs between:
  - Accuracy
  - Interpretability
  - Complexity

## **Business Impact**
This model enables Wallace Communications to:
- Target high-probability customers
- Reduce unnecessary call centre costs
- Improve campaign efficiency
- Increase conversion rates

## **Project Pipeline Structure**
flowchart TD

A[Raw Dataset] --> B[Initial EDA]
B --> B1[Check data types]
B --> B2[Check missing values]
B --> B3[Basic distributions]

B --> C[Data Cleaning]
C --> C1[Filter UK customers]
C --> C2[Remove invalid values]
C --> C3[Standardise columns]
C --> C4[Drop irrelevant columns]

C --> D[Post-Cleaning EDA]
D --> D1[Histograms]
D --> D2[Bar Charts]
D --> D3[Behaviour analysis]

D --> E[Feature Engineering]
E --> F[Train/Test Split]
F --> G[SMOTE]
G --> H[Preprocessing]
H --> I[Model Training]
I --> J[Evaluation]
J --> K[Insights]

<img width="3185" height="2099" alt="mermaid-diagram " src="https://github.com/user-attachments/assets/33ab81f0-da8d-4e87-96a6-8444cf0830bf" />

## **Technologies Used**
- Python
- Pandas
- NumPy
- Scikit-learn
- Imbalanced-learn (SMOTE)
- Matplotlib
- Seaborn
- SciPy

## **How to Run**
- Clone the repository
- Install dependencies:
  - pip install pandas numpy scikit-learn imbalanced-learn matplotlib seaborn
- Update dataset path in the script
- Run the notebook/script

## **Author**
Ayodeji Fajemiseye
Data Analyst/Machine Learning Practitioner

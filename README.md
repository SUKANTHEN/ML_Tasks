# 
Machine Learning Task Solution Repo

### Methodology:

1. Data Loading (01_dataloader.ipynb): Loaded data from db/ directory into dataframes for further analysis.

2. Exploratory Data Analysis (EDA) and Cleaning (02_EDA.ipynb): Conducted comprehensive EDA, addressing missing values and outliers. Visualizations provided insights into data distribution and relationships.

3. Modeling with Catboost (03_Modelling.ipynb): Utilized Catboost for predictive modeling. Explored feature importance for better interpretability.


### Key Findings:

1. **Exploratory Data Analysis (EDA)**:

   Identified patterns and trends, contributing to a better understanding of the dataset. Notable findings include:
   * `Opened`:
Conversion Rate (Opened): The proportion of emails that were opened is 114 out of 154, resulting in a conversion rate of approximately 74.03%. This indicates that a significant portion of recipients engaged with the email by opening it.

   * `Meeting Link Click`:
Conversion Rate (Meeting Link Click): Among those who opened the email (114), 46 individuals clicked on the meeting link. The conversion rate for meeting link clicks among those who opened the email is approximately 40.35%. This suggests a positive engagement level, as a substantial portion of those who opened the email proceeded to interact further by clicking on the meeting link.
Responded:

   * `Conversion Rate (Responded)`: Out of the total opened emails (114), 8 recipients responded. The conversion rate for responses among those who opened the email is approximately 7.02%. While responding represents a deeper level of engagement than simply opening or clicking, the lower conversion rate indicates that responding is a less common action.


2. **Modeling with Catboost**:
   Achieved an Accuracy Score of 84%. However, the model is biased towards prediction of positive classes. The model is overfitting.
   ### Issues with the Mail Opening Prediction Model and Possible Solutions:

    * `Overfitting`: The model exhibits overfitting, failing to accurately predict negative cases during testing. This may stem from an imbalance in the training data, with the negative class (0) being a minority. Strategies like data augmentation or additional data collection could address this issue.
    
    * `Sample Size`:  The reduced performance might be attributed to a limited number of samples. Increasing the dataset size through techniques like augmentation or more data collection can aid the model in generalizing better to unseen instances.

    *  `Raw Data Usage and Data Cleaning for Performance Boosting`: The model, CatBoost, is trained on raw data. Exploring various NLP data cleaning and preprocessing techniques can potentially enhance the classifier's performance. Text Standardization, Stopword Removal, non-utf-8 encoded character removal other NLP text cleaning can help in enhancing the performance.
    
    * `Model Interpretability`:Consider using RandomForest and other simpler algorithms for model interpretation using tools like ELI5. This can provide insights into the significant words influencing predictions.
    
    * `Complexity of Algorithms`:Using deep learning approaches and state-of-the-art embeddings can help capture the sematicity (context) of the data and predict accordingly. To capture bi-directional context, trying out Bi-directional LSTMs can help.

# E-mail Engagement Analysis and Modeling

## Methodology

1. **Data Loading (`01_dataloader.ipynb`):**
   Loaded data from `db/` directory into dataframes for further analysis.

2. **Exploratory Data Analysis (EDA) and Cleaning (`02_EDA.ipynb`):**
   Conducted comprehensive EDA, addressing missing values and outliers. Visualizations provided insights into data distribution and relationships.

3. **Modeling with Catboost (`03_Modelling.ipynb`):**
   Utilized Catboost for predictive modeling. Explored feature importance for better interpretability.

## Key Findings

### Exploratory Data Analysis (EDA)

- **Conversion Rate (Opened):**
  The proportion of emails that were opened is 114 out of 154, resulting in a conversion rate of approximately 74.03%.

- **Conversion Rate (Meeting Link Click):**
  Among those who opened the email (114), 46 individuals clicked on the meeting link, with a conversion rate of approximately 40.35%.

- **Conversion Rate (Responded):**
  Out of the total opened emails (114), 8 recipients responded, resulting in a conversion rate of approximately 7.02%.

### Modeling with Catboost

Achieved an Accuracy Score of 84%. However, the model is biased towards prediction of positive classes, indicating overfitting.

#### Issues with the Mail Opening Prediction Model and Possible Solutions

1. **Overfitting:**
   The model exhibits overfitting, potentially due to an imbalance in the training data. Strategies like data augmentation or additional data collection could address this issue.

2. **Sample Size:**
   The reduced performance might be attributed to a limited number of samples. Increasing the dataset size through techniques like augmentation or more data collection can aid the model in generalizing better.

3. **Raw Data Usage and Data Cleaning:**
   Exploring various NLP data cleaning and preprocessing techniques can potentially enhance the classifier's performance. Text Standardization, Stopword Removal, and other NLP text cleaning can be explored.

4. **Model Interpretability:**
   Consider using RandomForest and other simpler algorithms for model interpretation using tools like ELI5 to provide insights into significant words influencing predictions.

5. **Complexity of Algorithms:**
   Exploring deep learning approaches and state-of-the-art embeddings can help capture the semanticity of the data. Trying out Bi-directional LSTMs can be considered for capturing bi-directional context.

## Next Steps

### 1. Text Classification Enhancements

- Develop text classifiers for `Responded` and `Meeting Click` features as target variables to create a comprehensive pipeline.

- These models will provide confidence scores, indicating the likelihood of various email events:
  - Predict the probability of the recipient opening the email.
  - Estimate the chances of the recipient clicking on the meeting link.
  - Determine the likelihood of receiving a response.

### 2. Airflow Pipeline Integration

- Integrate these classifiers into an Airflow pipeline, enabling efficient and scheduled processing of a large volume of emails.

- Consider aspects like parallel or sequential execution, task dependencies, monitoring and logging, scalability, scheduling, integration with MLflow or similar tools, automated notifications, error handling, and security measures.

### 3. Containerization Techniques

- Use Docker to encapsulate ML models for consistent deployment across environments.

- Leverage Docker's portability, scalability, and versioning benefits.

- Integrate containers into CI/CD pipelines for automated testing and deployment.

### 4. Post-deployment Strategies

- Implement a monitoring solution for real-time model performance tracking.

- Explore model retraining strategies based on new data patterns.

- Consider A/B testing to evaluate the effectiveness of model updates.

- Establish a feedback loop to gather insights from end-users for continuous improvement.

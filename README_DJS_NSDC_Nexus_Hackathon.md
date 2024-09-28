
# DJS NSDC Nexus Hackathon - ML Model for Value Prediction

## Project Overview

This project was developed as part of the **DJS NSDC Nexus Hackathon**, where the objective was to build a machine learning model capable of predicting a target value based on a provided dataset. We utilized **LightGBM** as the primary machine learning algorithm to handle classification tasks due to its efficiency and performance in handling large datasets and categorical features.

The dataset provided is related to drug-related data, with features describing various drug attributes. The aim is to predict the `Target_Status` based on these attributes.

## Why LightGBM?

LightGBM (Light Gradient Boosting Machine) was chosen for this project due to several key advantages:

- **Efficiency**: LightGBM is designed to be highly efficient with large datasets, especially when they contain categorical features. Its histogram-based algorithm makes it faster than traditional gradient-boosting models.
- **Handling of Categorical Features**: Unlike some machine learning models that require one-hot encoding for categorical data, LightGBM can directly handle categorical features, leading to better performance and simpler preprocessing.
- **Scalability**: LightGBM is scalable for large datasets and distributed learning, making it a great choice for this problem, which involves thousands of data points and many categorical variables.
- **Accuracy**: It consistently delivers high accuracy, and in our tests, it performed exceptionally well with over 99% accuracy.

## Model Description

The project uses a LightGBM classifier to predict the `Target_Status` of the given data points. The model was trained using cross-validation with 4 folds to ensure robustness and prevent overfitting. The steps involved in model development are:

1. **Data Loading**: 
   - Training and test datasets are loaded.
   - Duplicate entries are checked, and data cleaning is performed (removal of unnecessary columns, handling of missing values, etc.).

2. **Preprocessing**:
   - Categorical features like `DRUGID`, `DRUGTYPE`, `PUBCHCID`, etc., are converted into appropriate data types for LightGBM processing.
   - The dataset is split into input features (`X`) and target labels (`y`).

3. **Model Training**:
   - A **Stratified K-Fold** cross-validation technique is applied to divide the dataset into four different folds, ensuring that the distribution of the target classes is maintained.
   - For each fold, the model is trained and evaluated using accuracy and F1 score as key performance metrics.
   
4. **Final Training and Prediction**:
   - After cross-validation, the model is trained on the entire dataset and used to predict values for the test data.
   - The results are saved in a CSV file (`submission_new3.csv`) for submission.

## Key Results

The LightGBM model demonstrated outstanding performance during cross-validation and final predictions:

- **Training Accuracy**: 99.09%
- **Testing Accuracy**: 99.12%
- **Average Validation F1 Score**: Achieved a strong F1 score across all validation folds, indicating high precision and recall.

This high level of accuracy reflects the effectiveness of LightGBM in handling the given dataset and accurately predicting the `Target_Status`.

## How to Use

1. **Clone the Repository**:
   ```bash
   git clone <repository-url>
   ```
2. **Install Required Dependencies**:
   Install the required libraries by running:
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the Notebook**:
   Open the Jupyter notebook and run the cells step-by-step. The model will train, validate, and then make predictions on the test set.

4. **Submission**:
   Once the predictions are made, the results are saved to `submission_new3.csv`.

## Conclusion

LightGBM proved to be an effective choice for this classification problem due to its speed, efficiency with categorical data, and strong predictive performance. With an accuracy of over 99% in both training and testing data, the model successfully meets the goals of the hackathon task, making it a reliable solution for predicting the target values.

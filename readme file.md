**X Education Lead Conversion Analysis**

This repository contains the code and data for analyzing and predicting lead conversion for X Education, an online course selling education company. The goal is to build a logistic regression model that assigns a lead score to each lead, indicating the likelihood of conversion to paying customers.

**Problem Statement**

X Education receives a significant number of leads, but the lead conversion rate is poor. The objective is to identify variables that contribute to a higher customer conversion rate. The logistic regression model will be used to assign lead scores, with higher scores indicating a higher chance of conversion.

**Data Preparation**

The following steps were taken to prepare the data for building the logistic regression model:

1. Missing Data Handling: Columns with 45% or more missing data were dropped. Missing values in continuous variables were imputed with the median, while missing values in categorical variables were imputed with the mode. For categorical variables with missing value counts exceeding the mode count, the missing values were replaced with 'Not mentioned'.
1. Grouping Infrequent Levels: In some categorical columns, levels with highly varying counts were grouped together. This step helps to avoid the model picking up on highly underrepresented dummy levels, reducing complexity and sparsity in the data.
1. Creating Dummy Variables: After exploratory data analysis, dummy variables were created for categorical variables. Since k-1 dummies can take care of all the information contained in a categorical

variable with k levels, one dummy was dropped from the dummies created for each column.

4. Data Split: The data frame was split into two parts: one for training the model and the other for validating the model.
4. Normalization: Numerical variables were normalized to prevent any disproportionate effect on the model's results.
4. Handling Class Imbalance: The given dataset had a lead conversion rate of 38.45%, which is neither exactly balanced (50-50 ratio) nor heavily imbalanced. Thus, no special treatment was required for this dataset.
4. Feature Selection: As the dataset contained 54 features, it was not feasible to use all the variables. Recursive Feature Elimination (RFE) was performed to eliminate a few features, and a set of 20 features were selected for model building.

**Repository Structure**

The repository is organized as follows:

- [Nutan1411/Lead-Scoring](https://github.com/Nutan1411/Lead-Scoring): Contains all the files.
- **main**: `.ipynb` file contains documenting of the data exploration, preprocessing, feature selection, and model building process.
- **src/**: Source code files for any scripts or functions used in the analysis.
- **README.md**: This file, providing an overview of the project.

**Getting Started**

To replicate the analysis or use the model:

1. Clone this repository:

bash

git clone https://github.com/Nutan1411/Lead-Scoring.git

2. Install the required dependencies:

**pip install -r requirements.txt**

install requirement from .ipynb file

3. Execute the .ipynb file in the specified order:

· **Lead_score_Nutan_Shivam_Samantha.ipynb**

**Results**

The logistic regression model achieved an accuracy of XX% in predicting lead conversion. The model provides lead scores that can be used to prioritize leads with a higher likelihood of conversion, potentially improving the overall lead conversion rate.

Evaluation metrics before and after choosing the optimum cut-off for conversion probability:!

- **Before Optimum Cut-off (0.5):**
- Accuracy: 93.4%
- Sensitivity: 88.8%
- Specificity: 96.3%
- **After Optimum Cut-off (0.3):**
- Accuracy: 93%
- Sensitivity: 93.7%

- Specificity: 92.6%

Predictions were made on the test set, and the model's performance was evaluated:

- **Test Set Performance:**
- Accuracy: 93.3%
- Sensitivity: 93%
- Specificity: 93.5%

By choosing the optimum cut-off for conversion probability at 0.3, the model achieved improved sensitivity, correctly predicting approximately 93.7% of the converted labels. The specificity decreased slightly to 92.6%, correctly predicting approximately 93.5% of the unconverted labels.![](Aspose.Words.30887d31-5cc2-40af-a0b1-5b7c4ff82467.002.png)

These results demonstrate that the logistic regression model is effective in identifying leads with a high likelihood of conversion. X Education can leverage this model to prioritize!

**Conclusion**

By analyzing the data, performing feature selection, and building a logistic regression model, X Education can better identify and prioritize promising leads. The model's performance was evaluated using various metrics before and after choosing the optimum cut-off for conversion probability.

Before choosing the optimum cut-off at 0.5, the model achieved an accuracy of 93.4%, with a sensitivity of 88.8% and a specificity of 96.3%. However, after selecting the optimum cut-off at 0.3, the model's performance improved. The accuracy decreased slightly to 93%, but the sensitivity increased to 93.7% and the specificity decreased to 92.6%.

Predictions were made on the test set, and the model's performance was further evaluated. The accuracy on the test set was 93.3%, with a sensitivity of 93% and a specificity of 93.5%. This means that the model is able to correctly predict approximately 93% of the converted labels and approximately 93% of the unconverted labels.

Overall, the logistic regression model provides valuable insights and predictions for lead conversion. X Education can utilize these predictions to focus their efforts on leads with a higher likelihood of conversion, thereby optimizing their sales and marketing strategies.

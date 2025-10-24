# 📘 Overview
This assignment introduces data loading and exploratory analysis using the Boston Housing dataset in Orange. The primary tasks involve downloading the dataset via the Datasets widget and saving it as housing.tab, followed by loading and inspecting the file to analyze its structure: 506 instances and 14 attributes (13 features as numeric inputs and 1 target for median home value). Each attribute is described, such as CRIM (per capita crime rate), RM (average rooms per dwelling), and MEDV (target: median value in $1000s). The goal is to understand data types (all numeric), roles (features vs. target), and basic metadata, laying the foundation for regression-based predictive modeling in data mining.

# ⚙️ Flow
## 1.Flowchart One: Use Datasets to Download Housing and Save as housing.tab
<img width="865" height="510" alt="image" src="https://github.com/user-attachments/assets/3d441d94-2037-46ad-a068-f7e70beccfba" />

## 2.Flowchart Two: Open housing.tab and Analyze the Number of Data Instances and Attributes (Features) in Housing, and Introduce the Meaning of Each Attribute
<img width="865" height="511" alt="image" src="https://github.com/user-attachments/assets/9f4573fc-bde9-4a56-b486-5c55b27b5bd9" />

Click on the File to view the attribute-related information of housing.tab. Name represents the name, Type represents the data type—this file's all attributes are of Type numeric, meaning they are all numerical values. Role represents whether it is a feature or target; feature represents general input attributes, target represents the goal output, which is the value obtained after completing data analysis.

<img width="865" height="513" alt="image" src="https://github.com/user-attachments/assets/d630d44a-d642-471d-ba54-3f005e66aac4" />

After clicking on the table, from the info on the left side and the table itself, you can see that this file has 506 data instances, with 13 features and 1 target. The target's data type is numeric, named MEDV, and this dataset has no missing values.

| Attribute Name | Attribute Meaning |
| :--- | :--- |
| `CRIM` | Per capita crime rate by town |
| `ZN` | Proportion of residential land zoned for lots over 25,000 sq.ft |
| `INDUS` | Proportion of non-retail business acres per town |
| `CHAS` | Charles River dummy variable (= 1 if tract bounds river; 0 otherwise) |
| `NOX` | Nitric oxides concentration (parts per 10 million) |
| `RM` | Average number of rooms per dwelling |
| `AGE` | Proportion of owner-occupied units built prior to 1940 |
| `DIS` | Weighted distances to five Boston employment centres |
| `RAD` | Index of accessibility to radial highways |
| `TAX` | Full-value property-tax rate per $10,000 |
| `PTRATIO` | Pupil-teacher ratio by town |
| `B` | the proportion of blacks by town |
| `LSTAT` | % lower status of the population |
 
## 3.Flowchart Two: Use Feature Statistics , Box Plot , and Correlations to Analyze Attributes, and Explain the Meaning of the Presented Results

<img width="865" height="470" alt="image" src="https://github.com/user-attachments/assets/85d6775c-cab9-47fe-8f31-0ef66866bb7f" />

Feature Statistics primarily lists some basic statistics, such as mean, mode, median, etc.; additionally, it includes distribution plots that allow one to quickly see the nature of the data distribution, such as observing that the CHAS attribute has only two values, the RM attribute shows a bell-shaped curve distribution, and the DIS attribute's distribution is right-tailed, etc.

<img width="865" height="514" alt="image" src="https://github.com/user-attachments/assets/5d42a874-a72f-4927-83d1-516ca3539aca" />

The Box Plot primarily allows one to observe the density of data distribution and symmetry, and it can also identify if there are anomalous data values.

<img width="865" height="201" alt="image" src="https://github.com/user-attachments/assets/4a4f26db-9dd1-40c4-a71c-f1a4c50942a5" />

The above figure is the Box Plot for the DIS attribute, where the blue shaded area represents the Q1-Q3 interval, the yellow line represents the median, and the median of the DIS attribute is 3.207450. The blue dividing line in the middle represents the mean, and the number behind it is the variance, meaning the mean of the DIS attribute is 3.795043, and the variance is 2.10363. The blue horizontal line represents the range of data distribution within outliers, and data exceeding this range are outliers. Finally, the blue dots on the left and right sides represent the maximum and minimum values of the entire dataset distribution. From this Box Plot, we can see that since the mean > median, it can be inferred that the distribution of this attribute is likely right-tailed. Additionally, the outlier degree of the maximum value is relatively large, so this value can be specifically identified for further inspection.

## 4.Flowchart Three: Split the Data into 80% Training and 20% Testing, Use the MAPE Performance Metric from Predictions to Find the Better Normalization Parameters for Linear Regression. Must List All Tried Results and Select the Best Parameter Value from Them.

MAPE

<img width="318" height="115" alt="image" src="https://github.com/user-attachments/assets/0a7ef439-4edd-42d6-867a-1964c490f1ca" />


Use the Data Sampler widget with "Sampling Type: Random" to divide the dataset into 80% training set and 20% testing set for unbiased evaluation.

<img width="819" height="644" alt="image" src="https://github.com/user-attachments/assets/3d05d13b-2d6c-4e41-a9a8-1244329b0001" />

The above values represent the results of performing L1 regularization (Lasso Regularization), where the α values at 0.001, 0.01, 1, and 100 all yield MAPE values of 0.169, indicating that on average, the predicted values have approximately 16.9% error compared to the actual values, which is within an acceptable range.

<img width="819" height="647" alt="image" src="https://github.com/user-attachments/assets/4cad0dfc-833a-48c3-aaab-b512d6d2693a" />

The above values represent the results of performing L2 regularization (Ridge Regularization), where the α values at 0.001, 0.01, 1, and 100 all yield MAPE values of 0.169, indicating that on average, the predicted values have approximately 16.9% error compared to the actual values, which is within an acceptable range.
From the above conclusion, it is known that if no data is deleted, adjusting the α value has little impact on MAPE, and the error mostly falls between 16-17%.

## 5.Flowchart Four: Delete less important features and explain the reason for deletion.By using correlation coefficients, remove attributes with relatively low correlation first.

<img width="782" height="594" alt="image" src="https://github.com/user-attachments/assets/9031ef59-fe4d-4ea4-bf82-8c18f420578f" />

By using the Select Column tool to remove unwanted attributes.


The Lasso Regularization after removing the four parameters with the lowest correlation (CHAS, DIS, B, ZN) is as follows:
<img width="400" height="343" alt="image" src="https://github.com/user-attachments/assets/174d69b1-944d-4348-abaf-5768ea4a6a4a" />

It was found that MAPE has increased, speculating that too many attributes may have been removed, so the next step is to delete only the attribute with the lowest correlation, CHAS, and the test results after removal are as follows:
<img width="393" height="337" alt="image" src="https://github.com/user-attachments/assets/0c03461e-2d10-475e-8884-3ba7320f221d" />

It was found that MAPE has decreased significantly, but it is still higher than before the deletion. The inference is that although the correlation coefficients of attributes like CHAS, B, etc., are relatively low in this linear regression model, the ±0.3 correlation coefficients still have some influence on the output value, therefore, deletion still leads to an increase in MAPE.










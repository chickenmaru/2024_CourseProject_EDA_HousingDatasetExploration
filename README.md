# Overview
This assignment introduces data loading and exploratory analysis using the Boston Housing dataset in Orange. The primary tasks involve downloading the dataset via the Datasets widget and saving it as housing.tab, followed by loading and inspecting the file to analyze its structure: 506 instances and 14 attributes (13 features as numeric inputs and 1 target for median home value). Each attribute is described, such as CRIM (per capita crime rate), RM (average rooms per dwelling), and MEDV (target: median value in $1000s). The goal is to understand data types (all numeric), roles (features vs. target), and basic metadata, laying the foundation for regression-based predictive modeling in data mining.

# Flow
## Flowchart One: Use Datasets to Download Housing and Save as housing.tab
<img width="865" height="510" alt="image" src="https://github.com/user-attachments/assets/3d441d94-2037-46ad-a068-f7e70beccfba" />

## Flowchart Two: Open housing.tab and Analyze the Number of Data Instances and Attributes (Features) in Housing, and Introduce the Meaning of Each Attribute
<img width="865" height="511" alt="image" src="https://github.com/user-attachments/assets/9f4573fc-bde9-4a56-b486-5c55b27b5bd9" />

Click on the File to view the attribute-related information of housing.tab. Name represents the name, Type represents the data type—this file's all attributes are of Type numeric, meaning they are all numerical values. Role represents whether it is a feature or target; feature represents general input attributes, target represents the goal output, which is the value obtained after completing data analysis.

<img width="865" height="513" alt="image" src="https://github.com/user-attachments/assets/d630d44a-d642-471d-ba54-3f005e66aac4" />

After clicking on the table, from the info on the left side and the table itself, you can see that this file has 506 data instances, with 13 features and 1 target. The target's data type is numeric, named MEDV, and this dataset has no missing values.

Attribute Name,Attribute Meaning
CRIM,Per capita crime rate by town
ZN,"Proportion of residential land zoned for lots over 25,000 sq.ft."
INDUS,Proportion of non-retail business acres per town
CHAS,Charles River dummy variable (= 1 if tract bounds river; 0 otherwise)
NOX,Nitric oxides concentration (parts per 10 million)
RM,Average number of rooms per dwelling
AGE,Proportion of owner-occupied units built prior to 1940
DIS,Weighted distances to five Boston employment centers
RAD,Index of accessibility to radial highways
TAX,"Full-value property-tax rate per $10,000"
PTRATIO,Pupil-teacher ratio by town
B,1000(Bk - 0.63)^2 where Bk is the proportion of blacks by town
LSTAT,% lower status of the population
MEDV (Target),Median value of owner-occupied homes in $1000's

## 

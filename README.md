# Analysis of Diabetes Risk

**Analysis of Diabetes Risk** is a comprehensive data analysis tool designed to streamline data exploration, analyze, and visualize impact of behavioural  and lifestyle factors on diabetes risk in India.

# ![CI logo](https://codeinstitute.s3.amazonaws.com/fullstack/ci_logo_small.png)


## Dataset Content
* The "Diabetes in Young Adults in India" dataset from Kaggle contains 100,000 record entries of synthetic but realistic data reflecting the prevalence of diabetes and associated factors among young adults (ages 15-25) in India. 

The dataset contains 100000 rows and 22 columns.

List of columns contains: ID, Age, Gender, Region, Family_Income, Family_History_Diabetes, Parent_Diabetes_Type, Genetic_Risk_Score, BMI, Physical_Activity_Level, Dietary_Habits, Fast_Food_Intake, Smoking, Alcohol_Consumption, Fasting_Blood_Sugar, HbA1c,Cholesterol_Level, Prediabetes, Diabetes_Type, Sleep_Hours, Stress_Level, Screen_Time.

There are no empty values.

## Project Plan
** Setup stage 0
* Set up the github repository and kanban board to track project files and progress respectively.
* Update readme file and jupyter notebook in Code Institute repository template.
* Upload the dataset "Diabetes in Young Adults in India" from kaggle into workspace.

* Start coding

** ETL Stage 1 (Data extraction, transformation and loading )
* Imported packages from commonly used python libraries 
* Checking and analyzing initial dataset information regarding column names, total number of rows and columns,  datatypes, empty values.
*Struggled with value count, tried to create a dictionary to store and display values in a more readable format.

**Data Validation
* Transforming dataypes into numeric datatype using encoder pipeline.
* Created a separate dictionary  to store and showcase unique values for categorical columns such as Gender, Region, Physical_Activity_Level, etc.
*Duplicate and missing values were checked.

** Data Cleaning
* Dropped unnecessary columns, i.e. columns that I was not going to use not for further analysis were dropped, including ID, Family_Income, Family_History_Diabetes, Parent_Diabetes_Type, Fasting_Blood_Sugar, Genetic_Risk_Score, Cholesterol_Level, Prediabetes, and Diabetes_Type.
* Dropped any NAN values as they were messing data viualistion later on.
Data Transformation
Pipeline Setup: A pipeline with an ordinal encoder was created to transform categorical values into numeric values.

*Encoding and mapping was done.



## Analysis techniques used
*Descriptive Statistics was done to generate a summary of common stats like mean, max and minimum values to provide an overview of the dataset.

*Correlation Analysis was calculated to understand the relationships between different variables in the dataset.

*Heatmap Visualization: A correlation heatmap was created to visually represent the relationships between variables.

** Data Visualization
*Several visualizations were created to explore and present the data insights.

*Heatmap correlation analysis showed the correlation between various variables such as Age, BMI, HbA1c, Physical_Activity_Level, Dietary_Habits, etc.
Positive correlations indicated a strong positive relationship between variables while negative correlations showcases there is a negative relationship between variables. No correlations means  little to no linear relationship between the variables.

*Scatter Plot: Age vs. HbA1c Levels by Gender showcased the distribution of HbA1c levels across different ages and genders was suppose to identify trends or anomalies in diabetes control among different demographics.
*Stacked Bar Plot visualization shows an overview of the average BMI across various regions, broken down by gender to highlight regional disparities in BMI influenced by lifestyle, diet, or access to healthcare.

* Box plot illustration was suppose to show the relationship between physical activity levels and diabetes outcomes but maybe because of data skew couldn't see mean value.


* My main issue was there was too much data and it would some time give errors of truncation. I struugled with the data visualisation part a lot.

* Use of generative AI tools to help with ideation, design thinking and code optimisation:  I used basic code understanding to anlyze the dataset and then would use own logic to write code and if it didn't work then ask Copilot to generate a working variation for what I want and then apply it, if it worked fine if not modify code until it met my needs.

## Ethical considerations
* There was no breach of data privacy.
 * No bias or unfairness issues with the data.

## Unfixed Bugs
* Please mention unfixed bugs and why they were not fixed. 
 * There is some Value error in mapping or replacing 'Sedentary' in the imputer, kept getting can't convert string into float
 # (Fixed) Tried ChatGPT to fix imputer code, it gave a cleaner code which is now working
       # Fill NaN values with 'Unknown' or handle them in another way
      
      diabetes_df['Physical_Activity_Level'] = diabetes_df['Physical_Activity_Level'].fillna('Unknown')
      diabetes_df['Physical_Activity_Level'] = diabetes_df['Physical_Activity_Level'].map({'Sedentary': 0, 'Moderate': 1, 'Active': 2})
      
      # Added another line of Copilot code to fix issue, -1 for unknown values
      diabetes_df['Physical_Activity_Level'] = diabetes_df['Physical_Activity_Level'].apply(
                   lambda x: {'Sedentary': 0, 'Moderate': 1, 'Active': 2}.get(x, -1))


* Many gaps in my knowledge, and I relied heavily on ChatGPT and Copilot to build this project.

Watching fellow peers work, helped to clear confusion. 

## Development Roadmap
* I wanted to make different functions for each section but started getting errors with the Diabetes dataframe so made the code shorter and simpler to follow.
* There was issue with converting 'Sedentary' string to float in the imputer, tried mapping and replacing to no avail, had to remove the code snippet all together, added an encoder pipelinr from Code Institute LMS instead.

## Main Data Analysis Libraries
* Pandas 
* Matplotlib
* Scit-learn
* Seaborn
* Category Encoder


## Credits 

* Dateset: https://www.kaggle.com/datasets/ankushpanday1/diabetes-in-youth-vs-adult-in-india
* Code Institute: www.learn.codeinstitute.net
* Microsoft Copilot: www.copilot.com
* ChatGPT: https://chatgpt.com/
* Python cheatsheet: https://realpython.com/pandas-python-explore-dataset/

### Content 

- Readme and Jupyter notebook()  was built using Code Institute sample Readme and Jupyter files.
- Importing packages, count values method, drop method, code snippet were taken from Code institute LMS.
- Checking and analyzing initial dataset code snippets were taken from website: https://www.dataquest.io/cheat-sheet/pandas-cheat-sheet/ 
- Copilot and ChatGPt were extensively used to make the overall code work especially for data visualisation


## Acknowledgements (optional)
* Thank you Vasi, Neil and all my classmates for their support.

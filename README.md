# Project XYZ

**Analysis of Diabetes Risk** is a comprehensive data analysis tool designed for medical professionals to streamline data exploration, analysis, and visualisation to analyze behavioural  and lifestyle factors on diabetes risk in India.

# ![CI logo](https://codeinstitute.s3.amazonaws.com/fullstack/ci_logo_small.png)


## Dataset Content
* The "Diabetes in Young Adults in India" dataset from Kaggle contains 100,000 record entries of synthetic but realistic data reflecting the prevalence of diabetes and associated factors among young adults (ages 15-25) in India. 

The dataset contains 100000 rows and 22 columns.

List of columns contains: ID, Age, Gender, Region, Family_Income, Family_History_Diabetes, Parent_Diabetes_Type, Genetic_Risk_Score, BMI, Physical_Activity_Level, Dietary_Habits, Fast_Food_Intake, Smoking, Alcohol_Consumption, Fasting_Blood_Sugar, HbA1c,Cholesterol_Level, Prediabetes, Diabetes_Type, Sleep_Hours, Stress_Level, Screen_Time.

There are no empty values.


## Hypothesis and how to validate?
* List here your project hypothesis(es) and how you envision validating it (them) 

## Project Plan
** Setup stage 0
* Set up the github repository and kanban board to track project files and progress respectively.
* Update readme file and jupyter notebook in Code Institute repository template.
* Upload the dataset "Diabetes in Young Adults in India" from kaggle into workspace.

* Start coding
** ETL Stage 1 (Data extraction, transformation and loading )
* Imported packages from commonly used python libraries 
* Checking and analyzing initial dataset information regarding column names, total number of rows and columns,  datatypes, empty values.
* Transforming dataypes into numeric datatype using imputer pipeline



## The rationale to map the business requirements to the Data Visualisations
* List your business requirements and a rationale to map them to the Data Visualisations

## Analysis techniques used
* List the data analysis methods used and explain limitations or alternative approaches.
Descriptive Analysis: Helped to get basis statistics mean, minimum and maxiumum values
* How did you structure the data analysis techniques. Justify your response.


* My main issue was there was too much data and it would some time give errors of truncation.

* Use of generative AI tools to help with ideation, design thinking and code optimisation:  I used basic code understanding to anlyze the dataset and then would use own logic to write code and if it didn't work then ask Copilot to generate a working variation for what I want and then apply it, if it worked fine if not modify code until it met my needs.

## Ethical considerations
* There was no breach of data privacy.
 * No bias or unfairness issues with the data.

## Unfixed Bugs
* Please mention unfixed bugs and why they were not fixed. 
 # There is some Value error in mapping or replacing 'Sedentary' in the imputer, kept getting can't convert string into float
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

### Heroku

* The App live link is: https://YOUR_APP_NAME.herokuapp.com/ 
* Set the runtime.txt Python version to a [Heroku-20](https://devcenter.heroku.com/articles/python-support#supported-runtimes) stack currently supported version.
* The project was deployed to Heroku using the following steps.

1. Log in to Heroku and create an App
2. From the Deploy tab, select GitHub as the deployment method.
3. Select your repository name and click Search. Once it is found, click Connect.
4. Select the branch you want to deploy, then click Deploy Branch.
5. The deployment process should happen smoothly if all deployment files are fully functional. Click now the button Open App on the top of the page to access your App.
6. If the slug size is too large then add large files not required for the app to the .slugignore file.


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
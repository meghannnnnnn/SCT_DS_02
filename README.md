# *Titanic Data Analysis🛳️*

Performed data cleaning and exploratory data analysis (EDA) on a Titanic dataset(train.csv) from Kaggle. Explore the relationships between variables and identify patterns and trends in the data.

## 🔴Producers:
1. *Import Libraries:*
   - pandas for data manipulation
   - numpy for numerical computations
   - seaborn for data visualization
   - matplotlib.pyplot for plotting

2. *Load Data:*
   - The script mounts your Google Drive and sets the path to the CSV file containing the Titanic passenger data.
   - It then reads the CSV file into a Pandas DataFrame named train_df.

3. *Summary Statistics:*
   - The code displays the first few rows of the DataFrame using head().
   - It then uses info() to get an overview of the data types and number of non-null values in each column.
   - Finally, it displays the column names using columns.
   - The script uses describe() to generate summary statistics for the numerical columns (PassengerId, Survived, Pclass, 
     Age, SibSp, Parch, and Fare).

4. *Data Cleaning:*
   - The script checks for missing values in each column using notnull().sum() and isnull().sum().
   - It then drops rows with too many missing values, keeping only rows with at least three non-missing values using 
     dropna().
   - For the 'Age' column, the script imputes the missing values with the mean age using fillna().
   - The script converts the categorical column 'Embarked' to a numerical feature using factorize().
   - It then interpolates the missing values in 'Embarked' using linear interpolation.
   - A new feature named 'FamilySize' is created to represent the total family size (including the passenger themselves) by adding 'SibSp' and 'Parch' and then adding 1.
   - The script drops the columns 'Name', 'Ticket', and 'Cabin' as they are unlikely to be significant predictors of survival.

5. *Data Exploration:*
   - The code describes the cleaned DataFrame using describe.T.round(2). This provides a summary of the numerical features 
     after cleaning.
   - It then displays the value counts for the categorical features 'Sex', 'Pclass', and 'Embarked' using value_counts().
   - The script uses hist() to visualize the distribution of the 'Age' and 'Fare' features.
   - It leverages seaborn's boxplot() function to compare the distribution of 'Age' across different survival classes.
   - A count plot is created using sns.countplot() to explore the relationship between 'Pclass' and 'Survived'.
   - The script uses barplot() from seaborn to visualize the survival rates by Age Group ('Child', 'Young Adult', 'Adult', 
     and 'Senior'). These groups are created using pd.cut() based on age ranges.
   - Finally, the code displays histograms for the cleaned 'Age' and 'Fare' distributions using hist().
   - It also uses sns.countplot() to visualize the distribution of 'Sex' and 'Embarked'.

*Note:* This script is a basic example of data analysis using Google Colab. You can further explore the data by creating additional features, performing machine learning tasks to predict survival, and fine-tuning the analysis based on your specific interests.


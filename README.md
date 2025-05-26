# datacleaning
To prepare the dataset for analysis and modeling, a comprehensive data cleaning process was followed:
1. Exploratory Data Profiling
    Utilized YData Profiling (formerly Pandas Profiling) to perform an initial EDA.
    Gained insights into correlations, missing values, and column data types, which guided the cleaning steps.
2. Missing Value Treatment
    Applied mean imputation to the age column to handle missing values, assuming a normal distribution and minimal skew.
3. Irrelevant Feature Removal
    Dropped non-informative or identifier columns: PassengerId, Ticket, and Name.
4. Categorical Encoding
    Sex column: Encoded using binary mapping (0 = male, 1 = female).
    Cabin column:
      Extracted the deck information (first character of the cabin).
      Replaced missing values with a placeholder label `U` (Unknown).
      Applied Label Encoding to convert the deck labels into numerical values.
5. Feature Engineering
    Combined SibSp and Parch columns into a single FamilySize feature:
     FamilySize = SibSp + Parch + 1
    This provided a more meaningful representation of family structure.
6. One-Hot Encoding
    Applied One-Hot Encoding to the Embarked column.
    Dropped one dummy variable to avoid multicollinearity (dummy variable trap).
7. Outlier Detection and Removal
    Visualized Fare, Age, and FamilySize using boxplots.
    Identified and removed lower and upper outliers using the IQR method.
8. Feature Scaling
    Applied Min-Max Normalization to Fare, Age, and FamilySize to scale them to the [0, 1] range, ensuring consistency and improving model convergence.



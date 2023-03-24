# Exploring Demographic Factors of Substance Use

The purpose of this project is to determine which identity marker(s) (if any) could be used to model and/or predict an individual’s levels of drinking, smoking, and drug use. The dataset examined contains demographic and other identity-based information on OK cupid users, as well as their written response to various short essays ([see link](https://www.kaggle.com/datasets/andrewmvd/okcupid-profiles))

### Data Wrangling & Cleaning

The dataset under anlysis contains many features with qualitative and quantitative data. Before any analyisis was performed, the data was cleaned by replacing or otherwise remove nans. The columns containing nan values were largely qualitative or text-based and they were cleaned based on whether it was safe to assume that a nan meant a zero or non value; if a row contained a nan  in the body type or diet category, for instance, that row was removed because it was not evident that this should mean a zero or average value. However, if the nan was in the category like number of offspring or pets, it was safe to assume the value could be zero.

### Augmenting Data

Along cleaning the nan values, categorical data (such as ethnicity, religion, orientation) were quantified through adding dummy columns to the data (columns that equaled 1 if that individual fit the category, and 0 otherwise). Additioanlly, certain columns that had values on a hierarchical scale (levels of drinking, smoking, drug use, and education) reassigned with values that fit the scale of that particular category (i.e. for levels of smoking, 'no' mapped to 0, 'when drinking' to 1, 'sometimes' to 2, 'yes' to 3, and 'trying to quit' to 4, since an individual trying to quit is likely smoking the most out of all categories). This would allow for machine learning algorithms to be implemented using purely quantitative data.

### Exploratory Analysis

An initial exploratory analysis was performed by to determine which individuals used substances;  by implementing a script that would print the percentages of individuals that fall within a certain category and by printing the correlation values of each substance use, it was determined that the highest correlation amongst substance use actually is among other substances (i.e. drinking is correlated with smoking and vice versa). 

### Machine Learning Applications: K-Means++ Classification & Support Vector Regression

To further explore the emergent groups and trends within substance use, machine learning algorithms for classification and regression were applied to the augmented dataset. K-Means++ was applied to split the data into 4 clusters, such that an individual's demographic data could be entered and the algorithm could predict their cluster and various attributes. Likewise, support vecotr machines were applied and iterated for to find the C and gamma parameters that yielded the maximum accuracy, achieving an average of 80% accuracy for predicting an individual's propensity for substance.

### Conclusions

While the most obvious trend of mutually exclusive substance use became emergent from the exploratory analysis and confirmed by the machine learning applications, there is still more to be uncovered in this dataset and other related sources of substance use information. As this project progresses, Naive Bayes theorem will be applied to determine the relative probabilities of individual traits and substance use to generate a more granular view of trends in isolated characteristics. 

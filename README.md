# Explainable-AI-Predictive-Modeling
Exploration of the Airline Passenger Satisfaction dataset from Kaggle, which includes 23 features and over 100,000 rows of traveler data

Data Preprocessing & Exploratory Data Analysis (EDA)

The initial phase focused on preparing the raw data for modeling and identifying core relationships:

    Data Cleaning: Missing values were handled using mean imputation, and categorical variables were transformed via label encoding.

    Feature Scaling: Numerical features were standardized using StandardScaler to ensure uniform influence across the model.

    Visualization: EDA included correlation heatmaps to identify feature relationships and count plots to examine the distribution of the target variable ('satisfied' vs. 'neutral/dissatisfied').

Dimensionality Reduction

Three distinct techniques were utilized to visualize high-dimensional data in a 2D space:

    PCA: Captured maximum variance but resulted in a single large cluster where satisfaction was best separated by a parabolic boundary.

    t-SNE: Preserved local structures, revealing three distinct clusters—two primary dissatisfied groups and one mixed group leaning toward satisfaction.

    UMAP: Provided the most superior results by preserving both local and global structures, creating the most defined and separated clusters.

Feature Selection & Model Performance

Using a Random Forest Classifier (RFC), the project compared different feature selection strategies to optimize the model:

    Baseline: Achieved 94.61% accuracy using all features.

    Filter Method (SelectFromModel): Reduced feature count by 1/3 with only a slight decrease in accuracy (94.42%), demonstrating high efficiency.

    Wrapper Method (RFE): Yielded the best results by increasing accuracy to 94.99% while simultaneously reducing the feature space by 1/3, indicating a highly discriminative subset of features.

Explainable AI

To understand why predictions were made, a Multi-Layer Perceptron (MLP) classifier was analyzed using interpretability tools:

    LIME vs. SHAP: Both tools identified Type of Travel, On-board Service, and Customer Type as the top three determinants of satisfaction.

    Observations:

        LIME was more computationally efficient, explaining individual instances without needing to truncate the data.

        SHAP provided a global view of feature impact but required data truncation due to high computational demands.

    Insights: The model is highly transparent but skewed, with a few key features driving most of the output.

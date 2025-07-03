# California Housing Data Analysis & Modeling

Welcome to my California Housing Data Analysis & Modeling project. In this repository, I explore, clean, and model the California Housing dataset, which I sourced directly from scikit-learn. This project documents my journey from understanding raw data to building predictive models, and it provides a clear narrative of the steps I took along the way.

## Table of Contents

- [Overview](#overview)
- [Dataset Story and Motivation](#dataset-story-and-motivation)
- [Data Loading & Exploration](#data-loading--exploration)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Outlier Detection and Removal](#outlier-detection-and-removal)
- [Modeling Approaches](#modeling-approaches)
  - [Linear Regression](#linear-regression)
  - [Random Forest Regression](#random-forest-regression)
- [Conclusion](#conclusion)
- [How to Run](#how-to-run)
- [License](#license)

## Overview

In this project, I performed an end-to-end analysis of the California Housing dataset. I began with basic data exploration to understand the dataset's features and summary statistics, followed by a comprehensive exploratory data analysis. Next, I addressed data quality by detecting and removing outliers with an IQR-based approach, and finally, I built both linear and non-linear models to predict housing prices.

## Dataset Story and Motivation

I have always been fascinated by real estate and how various factors contribute to housing prices. When I discovered the California Housing dataset, it presented a unique opportunity to dive into a real-world problem. The dataset includes features such as median income, house age, room counts, and geographical coordinates—all of which provide insights into the diverse housing market of California.

The story behind this dataset is one of complexity and nuance. Despite being clean, the dataset required careful handling of outliers and thoughtful feature engineering, as the influence of geography and socioeconomic factors are not straightforward. Through this analysis, I aimed to build models that not only predict housing prices accurately but also offer interpretability regarding what drives these prices.

## Data Loading & Exploration

I started by loading the dataset using scikit-learn and converting it into a Pandas DataFrame. Here are some key details:
- **Observations:** 20,640 entries
- **Features:** 8 features (MedInc, HouseAge, AveRooms, AveBedrms, Population, AveOccup, Latitude, Longitude)
- **Target:** Price (with a known cap at >= 5.0)

I checked for missing values and computed summary statistics to understand the distribution and range of each feature.

## Exploratory Data Analysis (EDA)

To get a better understanding of the data:
- I plotted histograms for each feature to assess their distributions.
- I generated a correlation matrix to highlight relationships between features, finding that **Median Income (MedInc)** had the strongest correlation with house prices.

This EDA step was crucial in forming my hypotheses about which features would be the best predictors in my models.

## Outlier Detection and Removal

Due to noticeable right-skewness in features like **Population**, **AveRooms**, and **AveOccup**, I applied an Interquartile Range (IQR) method to detect and remove outliers. I experimented with different multipliers for various features to ensure I removed true anomalies without discarding valid data points. This careful outlier treatment improved the overall quality of my dataset and contributed to more stable model performance.

## Modeling Approaches

### Linear Regression

I started with a simple linear regression model, using **Median Income (MedInc)** as the sole predictor. This provided a solid baseline. Later, I extended the model to include multiple features such as **AveRooms, HouseAge, Latitude, and Longitude**. Although these models assumed linear relationships, they gave clear insights into the direct effects of each predictor on the target variable.

### Random Forest Regression

Recognizing the limitations of linear models in capturing non-linear relationships—especially those tied to geographic factors—I transitioned to a Random Forest regression model. This non-linear approach significantly reduced prediction error (RMSE) and provided a deeper understanding of feature importance, reaffirming that both income and location are key drivers of housing prices.

## Conclusion

This project demonstrates a comprehensive workflow from data exploration and cleaning to model building and evaluation. Key takeaways include:
- **Data Quality:** Effective outlier removal can greatly enhance model performance.
- **Model Comparisons:** While linear models offer interpretability, non-linear models like Random Forests capture the complexity of real estate pricing more effectively.
- **Insights:** Median income and geographic features are the most influential factors in determining housing prices in California.

I hope this analysis provides a useful reference for anyone interested in housing data analytics and predictive modeling.

## How to Run

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/a-kossakowski/ml_california_housing
   
2. **Navigate to the Project Directory:**
   ```bash
   cd ml_california_housing
   
3. **Install the Required Libraries:**
   ```bash
   pip install -r requirements.txt

4. **Run the Notebook: Open the Jupyter Notebook to explore the analysis step-by-step (or use the .html version):**
   ```bash
   jupyter notebook ml_california_housing.ipynb


## License

Please refer to [LICENSE](LICENSE.md) file.

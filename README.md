# Asteroid Hazard Classification Project

## Objective
This project aims to predict whether an asteroid is hazardous to Earth based on its physical characteristics and orbital parameters using machine learning techniques. The dataset contains information about Near-Earth Objects (NEOs), including estimated diameter, relative velocity, miss distance, absolute magnitude, and hazardous classification.

## Dataset
The dataset used in this project is sourced from [NASA's Nearest Earth Objects dataset on Kaggle](https://www.kaggle.com/datasets/sameepvani/nasa-nearest-earth-objects). It includes the following features:
- `id`: Unique identifier for the asteroid
- `name`: Name of the asteroid
- `est_diameter_min`: Minimum estimated diameter (in kilometers)
- `est_diameter_max`: Maximum estimated diameter (in kilometers)
- `relative_velocity`: Relative velocity (in km/s)
- `miss_distance`: Distance from Earth (in kilometers)
- `orbiting_body`: Orbiting body (all Earth in this dataset)
- `sentry_object`: Monitoring status (True/False)
- `absolute_magnitude`: Brightness measurement
- `hazardous`: Binary classification (True/False)

## Project Structure
The project is organized into the following key sections:
1. **Data Loading and Initial Exploration**
   - Load the dataset and inspect basic statistics
   - Examine class distribution (9.73% hazardous, 90.27% non-hazardous)

2. **Data Preprocessing**
   - Handle missing values (none found in this dataset)
   - Clean data and remove duplicates
   - Encode categorical variables (hazardous, sentry_object)
   - Scale numerical features using StandardScaler

3. **Exploratory Data Analysis (EDA)**
   - Univariate analysis of target variable and feature distributions
   - Bivariate analysis including correlation heatmaps
   - Outlier detection and analysis

4. **Model Building**
   - Binary classification to predict hazardous status
   - Potential models to explore: Logistic Regression, Random Forest, SVM, etc.

5. **Model Evaluation**
   - Metrics: Accuracy, Precision, Recall, F1-score, ROC-AUC
   - Address class imbalance if necessary

## Key Findings from EDA
- The dataset contains 90,836 asteroids, with 8,840 (9.73%) classified as hazardous
- Numerical features show wide ranges in values, suggesting scaling is important
- No missing values were found in the dataset
- The target variable is imbalanced (more non-hazardous than hazardous examples)

## Dependencies
- Python 3.x
- Key libraries:
  - pandas
  - numpy
  - matplotlib
  - seaborn
  - scikit-learn

## How to Run
1. Clone the repository
2. Install required dependencies
3. Run the Jupyter notebook `Mini_Project_Grp1.ipynb` sequentially

## Future Work
- Implement additional feature engineering
- Experiment with different classification algorithms
- Address class imbalance using techniques like SMOTE or class weighting
- Deploy the model as a web application for real-time predictions

## Contributors
[Your Name/Team Name]

## License
[Specify license if applicable]

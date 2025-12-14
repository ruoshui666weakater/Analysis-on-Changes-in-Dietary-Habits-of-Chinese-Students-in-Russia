# Analysis on Changes in Dietary Habits of Chinese Students in Russia

![Project Banner](https://via.placeholder.com/1200x300?text=Chinese+Students+Dietary+Habits+in+Russia) <!-- You can replace this with an actual banner image if available -->

## Overview

This repository contains the materials for a research project analyzing the changes in dietary habits among Chinese students studying in Russia. The study explores demographic factors, adaptation timelines, consumption patterns, and attitudes toward dietary shifts using survey data from 62 participants. The analysis includes data preprocessing, visualizations, correlation analysis, and predictive modeling (regression and classification) to forecast diet structure changes and positive attitudes toward these changes.

Key findings:
- Most students experience moderate to large dietary changes after moving to Russia.
- Factors like stay duration, regional origin (North vs. South China), and daily habits influence adaptation.
- Machine learning models (e.g., Random Forest Classifier) achieve up to 79% ROC-AUC in predicting positive attitudes.

This project was conducted by Group AP as part of an academic assignment.

## Table of Contents

- [Overview](#overview)
- [Repository Structure](#repository-structure)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Data Description](#data-description)
- [Analysis Pipeline](#analysis-pipeline)
- [Results and Visualizations](#results-and-visualizations)
- [Predictive Modeling](#predictive-modeling)
- [Contributors](#contributors)
- [License](#license)

## Repository Structure

- `presentation_slides.pdf`: PDF slides presenting the project overview, methodology, findings, and conclusions.
- `script.ipynb`: Jupyter Notebook containing the full data analysis script, including data loading, preprocessing, visualizations, and machine learning models.
- `presentation_video.mp4`: Video presentation explaining the project and key insights.
- `raw_data.xlsx`: Raw survey data in Excel format (originally from an online survey). Contains responses from 62 Chinese students in Russia. (Note: The file path in the script is hardcoded; update it to your local path when running.)

## Requirements

To run the analysis script (`script.ipynb`), you'll need:

- Python 3.12+
- Jupyter Notebook or JupyterLab
- Libraries:
  - pandas
  - numpy
  - matplotlib
  - seaborn
  - scikit-learn (for models like LinearRegression, SVR, RandomForest, GradientBoosting)
  - warnings (standard library)

These are listed in the script's import section.

## Installation

1. Clone the repository:
git clone https://github.com/your-username/chinese-students-dietary-habits-russia.git
cd chinese-students-dietary-habits-russia

2. Install dependencies (recommended in a virtual environment):
python -m venv env
source env/bin/activate  # On Windows: env\Scripts\activate
pip install pandas numpy matplotlib seaborn scikit-learn


3. Launch Jupyter

# jupyter notebook
Open `script.ipynb` in your browser.

## Usage

1. **Update Data Path**: In `script.ipynb`, change the file path in `pd.read_excel()` to point to `raw_data.xlsx` in your local directory (e.g., `"raw_data.xlsx"`).

2. **Run the Notebook**: Execute cells sequentially. The script will:
- Load and preprocess the data.
- Generate visualizations (demographics, changes, comparisons, correlations).
- Train and evaluate regression/classification models.

3. **View Outputs**: Plots will display inline in Jupyter. Models output performance metrics (e.g., R², ROC-AUC).

4. **Presentation Materials**: Open `presentation_slides.pdf` for slides or play `presentation_video.mp4` for the video demo.

## Data Description

The raw data (`raw_data.xlsx`) is from an online survey with 62 responses. It includes 122 columns covering:

- **Demographics**: Region (North/South China), Gender, Academic Grade, Stay Duration in Russia.
- **Dietary Changes**: Degree of change, adaptation time, weight changes, attitudes.
- **Consumption Comparisons**: Changes in spicy level, vegetables, meat, seafood, fast food (China vs. Russia).
- **Habits**: Binary indicators for daily intake (e.g., vegetables, fruits, meat, water).
- **Other**: Meal times, physical activity, alcohol/coffee consumption, etc.

Data is encoded ordinally (e.g., 1-5 scales for changes: 1 = Significant Decrease, 5 = Significant Increase). Missing/invalid values (-3) are handled via median/mode imputation and clipping.

Sample headers (partial, in Chinese with translations):
- '序号' (ID)
- '1、您来自中国的哪里？' (Region in China)
- '2、您的性别是？' (Gender)
- '15、您认为你搬到俄罗斯后，你的饮食结构发生了变化吗？' (Diet Structure Change)
- And more (full list in the user query).

## Analysis Pipeline

1. **Data Loading**: Read Excel file.
2. **Preprocessing**: Select core columns, handle missing values, encode categoricals to numerical scales, rename to English.
3. **Exploratory Data Analysis (EDA)**: Generate plots for demographics, changes, comparisons, habits, and correlations.
4. **Modeling**: 
- Regression: Predict diet change degree.
- Classification: Predict positive attitude (binary).

## Results and Visualizations

The script generates several plots:
- **Demographics**: Pie charts and bar plots for region, gender, grade, stay duration.
- **Dietary Changes**: Bar plots for change degree, attitudes, weight, adaptation time.
- **Consumption Comparisons**: Bar plots for changes in specific food types.
- **Habits Comparison**: Percentage bar plots for China vs. Russia habits.
- **Correlation Matrix**: Heatmap of variable correlations.
- **Model Evaluations**: Bar plots for metrics, scatter plots (actual vs. predicted), ROC curves.

Example insights:
- 60%+ from South China; balanced gender.
- Moderate changes common; adaptation takes 1-3 months for most.
- Increased vegetable/seafood consumption in Russia.

## Predictive Modeling

- **Regression** (Predict Diet Structure Change): Models compared (Linear, SVR, Random Forest, Gradient Boosting). Best: SVR (R² ≈ -0.17, indicating room for improvement due to small dataset).
- **Classification** (Predict Positive Attitude): Binary (positive if score ≥4). Models compared. Best: Random Forest (ROC-AUC ≈ 0.79).
- Feature Importance (from best classifier): Top features include stay duration, adaptation time, consumption changes.

Models use 70/30 train-test split, standardization, and cross-validation.

## Contributors

- Group AP (Academic Project Team)
- Feel free to contribute by forking and submitting pull requests!

## License

This project is licensed under the MIT License.

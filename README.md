
# 🏠 NYC Airbnb Price Prediction Using Linear Regression

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-Linear%20Regression-orange?logo=scikitlearn)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas)
![Project](https://img.shields.io/badge/Project-AIML%20Minor-blue)

## 📌 Project Overview

This project focuses on predicting the nightly prices of Airbnb listings in New York City using **Linear Regression**, a supervised machine learning algorithm.

The project uses the `AB_NYC_2019.csv` dataset to explore listing information, perform data cleaning and preprocessing, train a regression model, and evaluate its performance using standard regression metrics.

The main goal is to understand how data analysis and machine learning can be used to estimate Airbnb prices and identify the limitations of price prediction.

## 🎯 Objectives

- Perform Exploratory Data Analysis (EDA) on Airbnb listing data.
- Identify and handle missing values.
- Analyze and treat outliers in price and minimum-night values.
- Prepare numerical and categorical features for machine learning.
- Build and train a Linear Regression model.
- Evaluate model performance using R², MAE, MSE, and RMSE.
- Analyze prediction errors for lower-priced and higher-priced listings.

## 📂 Project Structure

```text
NYC-Airbnb-Price-Prediction/
│
├── project2.ipynb
├── AIML_Minor_Project_2_Airbnb_Summary_Report_Completed.docx
├── README.md
└── AB_NYC_2019.csv   (optional, if permitted)
```

## 📊 Dataset Description

**Dataset name:** AB_NYC_2019.csv

The dataset contains Airbnb listing information for New York City, including:

- `neighbourhood_group` – Borough or larger location group.
- `room_type` – Type of room offered.
- `price` – Nightly listing price; the target variable.
- `minimum_nights` – Minimum number of nights required.
- `number_of_reviews` – Total reviews received.
- `reviews_per_month` – Average reviews per month.
- `calculated_host_listings_count` – Number of listings managed by the host.
- `availability_365` – Number of days the listing is available in a year.

The original dataset contains **48,895 rows and 16 columns**.

**Dataset source:** [Search for AB_NYC_2019 on Kaggle](https://www.kaggle.com/datasets/dgomonov/new-york-city-airbnb-open-data)

If the CSV file is not included in this repository, download it from the source above and place it in the project folder before running the notebook.

## 🛠️ Technologies Used

- **Python** – Programming language.
- **Pandas** – Data manipulation and analysis.
- **NumPy** – Numerical operations.
- **Matplotlib** – Data visualization.
- **Seaborn** – Statistical plots.
- **Scikit-learn** – Model training, data splitting, and evaluation.
- **Jupyter Notebook / Google Colab** – Development environment.

## ⚙️ Project Workflow

### 1. Exploratory Data Analysis

- Checked dataset dimensions and column names.
- Examined data types and descriptive statistics.
- Identified missing values and their percentages.
- Used plots to understand the distribution of important variables.

### 2. Data Cleaning

- Removed irrelevant identifiers and text columns from the model inputs.
- Handled missing values in `reviews_per_month`.
- Set missing monthly review values to zero for listings with no reviews.
- Filled remaining missing values in that feature using the median.

### 3. Outlier Treatment

- Examined `price` and `minimum_nights` using boxplots.
- Removed zero-priced listings and listings above the 95th percentile of price.
- Applied the notebook's minimum-night filtering rules to reduce extreme values.

### 4. Feature Engineering and Encoding

- Selected useful features for price prediction.
- Applied one-hot encoding to `neighbourhood_group` and `room_type`.
- Dropped the first category during encoding to reduce redundant features.
- Used `price` as the target variable.

### 5. Model Training

- Split the prepared dataset into training and testing sets.
- Used an 80:20 train-test split.
- Set `random_state=42` for reproducibility.
- Trained a Linear Regression model using Scikit-learn.

### 6. Model Evaluation

The model was evaluated using:

- **R² Score:** Measures how much variation in the target is explained by the model.
- **MAE:** Measures the average absolute difference between actual and predicted prices.
- **MSE:** Measures average squared prediction error.
- **RMSE:** Represents the square root of MSE and expresses error in the target's units.

### 7. Residual Analysis

- Plotted actual versus predicted prices.
- Examined residuals to identify prediction patterns.
- Compared mean absolute error across different price groups.

## 📈 Model Performance

The Linear Regression model achieved the following results on the test dataset:

| Evaluation Metric | Result |
|---|---:|
| R² Score | 0.487 |
| Mean Absolute Error (MAE) | $38.32 |
| Mean Squared Error (MSE) | 2,760.62 |
| Root Mean Squared Error (RMSE) | $52.54 |

### Understanding the Results

- **R² Score = 0.487:** The model explains approximately 48.7% of the variation in test-set prices.
- **MAE = $38.32:** Predictions differ from actual prices by about $38.32 per night on average.
- **MSE = 2,760.62:** Larger prediction errors receive greater weight because errors are squared.
- **RMSE = $52.54:** The square root of the average squared error is approximately $52.54 per night.

These results indicate that Linear Regression provides a useful baseline, but Airbnb prices are influenced by factors that the model does not fully capture.

## 🔍 Key Findings

- The model performs better for lower-priced listings than for the most expensive listings.
- The highest price group has noticeably larger prediction errors.
- Linear Regression can identify general price patterns but may not capture complex relationships between listing features and price.
- Additional feature engineering and alternative regression algorithms may improve prediction accuracy.

## ▶️ How to Run the Project

### Option 1: Google Colab

1. Download or clone this repository.
2. Open `project2.ipynb` in Google Colab.
3. Download `AB_NYC_2019.csv` from the dataset source if it is not included.
4. Upload the CSV file to your Colab session or update the notebook's dataset path.
5. Run the notebook cells in order.

### Option 2: Run Locally

Install the required libraries:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

Start Jupyter Notebook:

```bash
jupyter notebook
```

Open `project2.ipynb`, ensure the CSV file is available at the path used in the notebook, and run the cells in sequence.

## 🚀 Future Improvements

- Compare Linear Regression with Decision Tree and Random Forest regression.
- Explore additional useful features and location-related information.
- Test different preprocessing and outlier-treatment strategies.
- Improve the model's accuracy for expensive listings.
- Use cross-validation to obtain a more reliable estimate of model performance.

## 📌 Conclusion

This project demonstrates the use of the machine learning workflow for Airbnb price prediction, from exploratory data analysis and data preprocessing to model training and evaluation.

The Linear Regression model achieved an R² score of **0.487** and an MAE of **$38.32**. Although the model provides a useful starting point, its prediction errors increase for higher-priced listings. Further experimentation with features and other regression algorithms could improve performance.

## 👩‍💻 Author

**Your Name:** Anushka Kiran Gundale
**Course:** B.Tech – Artificial Intelligence and Machine Learning  
**Project:** AIML Minor Project 2  
**Academic Year:** 2026–2027

---

⭐ If you find this project useful, feel free to star the repository!

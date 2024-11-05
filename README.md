# Machine Learning Project Report - Muhammad Zhafran Ghaly

## Project Domain

I chose the domain of Economics and Business for this project titled **Predictive Analytics of Bank BNI (BBNI) stock**.

### Background

Stock investment is a popular choice for individuals looking to invest their wealth aside from real assets such as gold, diamonds, or land. Stocks represent a certificate of ownership for individuals or institutions in a company. An investor may choose this type of investment because it can provide both economic and non-economic benefits to shareholders.

As the economy evolves, many companies expand their operations. To achieve this goal, companies require significant funding. To meet this funding need, efforts are required to seek additional capital to inject into the company as a replacement or supplement to the funds currently being utilized or for the development and expansion of the business sector. One aspect evaluated by the public in investments is the company's financial performance, which is measured by its financial statements. Therefore, companies consistently publish their financial reports so that prospective investors can understand how the company is performing and its future prospects. To facilitate this for investors, I created **Predictive Analytics of Bank BNI (BBNI) stock**, which will help new investors as a benchmark for investing using Machine Learning continuously or through Time Series Forecasting/Regression.

The Forecasting method is a technique used for planning and controlling production within accounting. Additionally, forecasting is defined as a tool for effective and efficient planning. In Machine Learning, Forecasting is a technique that can be used to calculate what will happen in the next month or even several years ahead.

## Business Understanding

### Problem Statements

Here are the problems identified:
- Can this predictive analytics serve as a guide for investments, and how can we analyze the price of Bank BNI (BBNI)?
- How do we select the appropriate algorithm and train the model for the best results on this data?
- How can we analyze and predict the price of Bank BNI (BBNI) using Forecasting techniques in Time Series?
- Is Bank BNI (BBNI) the only stock that can be predicted in this case?

### Goals

The goals are as follows:
- To provide predictive analytics that can guide both new and experienced investors in the investment field.
- By training the model on several algorithms used, we will obtain results and then select the best one.
- After achieving the desired training results, we can apply it to Bank BNI for investment and have a reliable reference for investing in that company.
- Not only Bank BNI (BBNI), but all banks/companies can also be analyzed and predicted if we wish to analyze the market globally or within our region.

### Solution Statements

To meet these goals, the following solutions can be implemented:
1. Conduct further analysis and exploration of the dataset, followed by visualization to gain strong insights:
   - Handle missing values in the dataset.
   - If outliers are present, they can be addressed using the IQR method.
   - Normalize the dataset to ensure that the data used is of high quality.
   - Build a regression model for predicting continuous numbers in stocks.

2. The following algorithms will be tried in the model:
   - K-Nearest Neighbors (KNN)
   - Support Vector Machine (Support Vector Regression)
   - Boosting Algorithm (Gradient Boosting Regression)

3. After all processes, we can add hyperparameter tuning using Grid Search techniques to ensure the model operates at its best performance and produces optimal results.

## Data Understanding

In this project, I used a public dataset from Kaggle titled **Indonesian Stock Dataset**, specifically from the folder `/daily/BBNI.csv` (https://www.kaggle.com/datasets/muamkh/ihsgstockdata).

The dataset is in .csv format, with a total of 5600 data points and 6 columns: (timestamp, open, low, high, close, and volume). Here is the explanation of each column:
- **timestamp**: Date corresponding to open, low, high, close, and volume.
- **open**: Opening price per day.
- **low**: Lowest price per day.
- **high**: Highest price per day.
- **close**: Closing price per day.
- **volume**: Transaction volume per day.

### Exploratory Data Analysis

Here is the data analysis, including correlation, outliers, and univariate/multivariate analysis:

- **Handling Outliers**  
  Below is a visualization of the numerical data displaying outliers only in the ***volume*** feature.

  ![before Outlier](https://user-images.githubusercontent.com/76243151/194744826-a1d83def-c6ea-4e86-8215-fcddcd964d07.png)  
  *Figure 1. Outlier Before*

  Outlier handling can be done using the IQR Method.

  ![after Outlier](https://user-images.githubusercontent.com/76243151/194744833-5b656ba6-7295-4ab7-8e4b-ed219f086ede.png)  
  *Figure 2. Outlier After*

- **Univariate Analysis**  
  We focus on the **close** column.

  ![U](https://user-images.githubusercontent.com/76243151/194744843-7533d009-43b3-4289-b74c-e7d1b640f149.png)  
  *Figure 3. Univariate Analysis*

- **Multivariate Analysis**  
  Results from the multivariate analysis.

  ![M](https://user-images.githubusercontent.com/76243151/194744856-37511b01-7495-4fb6-abd8-d82160d81d46.png)  
  *Figure 4. Multivariate Analysis*

  From Figure 4, the **Close** column has a strong correlation with the **High, Open, Low, and Close** columns. Meanwhile, **Close** has a weaker correlation with the **Volume** column.

- **Correlation Heatmap**  
  To clarify the correlation, we use a heatmap.

  ![Heatmap](https://user-images.githubusercontent.com/76243151/194744863-330fd3fb-6a8a-46ab-a5a3-46bf56487e62.png)  
  *Figure 5. Correlation Heatmap*

  In Figure 5, the **Close** column has a strong positive correlation with all other features, indicated by the value **1**.

## Data Preparation

The next stage in data processing:

### Handling Missing Values

The dataset does not have any missing values. If there were any, they could be handled by either deleting them or filling in the missing values with the mean using the SimpleImputer library.

### Splitting the Dataset

The processed dataset is split into training and test data with a **80:20** ratio.

### Removing Unnecessary Features

We only need the **high, low, open, and close** columns, so the **volume** column is removed.

### Normalizing Data

In this stage, we use **MinMaxScaler** to transform the data into the range of **0** to **1**.

## Modeling

In this stage, we will use three algorithms: **Support Vector Regression, Gradient Boosting, and KNN**.

### Support Vector Regression 

- **Advantages**: More effective on high-dimensional data, memory efficient.
- **Disadvantages**: Difficult to use on large-scale data.

### Gradient Boosting

- **Advantages**: Produces more accurate modeling results, stable model.
- **Disadvantages**: Reduces model interpretability, high computational time.

### K-Nearest Neighbors (KNN)

- **Advantages**: Can handle noisy data, effective on large datasets.
- **Disadvantages**: Sensitive to outliers, vulnerable to less informative features.

#### Algorithm Implementation

For this project, the K-Nearest Neighbors model was selected because it produced the lowest error (0.00001) compared to other models.

## Evaluation

The metrics used for evaluation are Mean Squared Error (MSE).

MSE = \(\frac{1}{n} \sum (Y' - Y)^2\)

...

## Conclusion

Based on the results and analyses conducted, predictive analytics using machine learning techniques can effectively aid investors in making informed decisions regarding Bank BNI (BBNI) stock investments.

## MSE Calculation

The formula for MSE (Mean Squared Error) is given by:

\[
MSE = \sum \frac{(Y' - Y)^2}{n}
\]

Where the variables are defined as follows:
- \(Y'\) = Predicted Value
- \(Y\) = Actual Value
- \(n\) = Number of Data Points

The results of the MSE model can be seen in Table 1.

| Index | Train MSE           | Test MSE            |
|-------|---------------------|---------------------|
| SVR   | 20.238573880982816  | 55.52692278397914   |
| KNN   | 16.68136160714286   | 51.30848214285714    |
| Gradient Boosting | 9.669640985095231  | 36.33649890753796   |

**Table 1. MSE of Models**

This table indicates that the smaller the MSE obtained by a model, the more optimal the algorithm used.

### MSE Visualization Plot

The following is a plot showing the MSE values for various algorithms used.

![MSE](https://user-images.githubusercontent.com/76243151/194744877-149efa1b-b568-48bf-911d-0114f691413d.png)

**Figure 6. MSE Visualization Plot**

It can be seen from Figure 6 that the algorithm most suitable for use is **Gradient Boosting**, as it has the smallest MSE value.

### Accuracy of MSE Models

The accuracy of the models can be seen in Table 2.

| Index | Accuracy (%)        |
|-------|---------------------|
| SVR   | 99.61126168219803   |
| KNN   | 99.64079455447617   |
| Gradient Boost | 99.74561188065324   |

**Table 2. Accuracy of MSE Models**

Table 2 shows the accuracy of each algorithm used, and we can conclude that **Gradient Boost** is the most optimal algorithm for models with an accuracy greater than 99%.

In this Predictive Analytics, all models performed very well with only very small differences among the three algorithms used. However, we will choose the model with the highest accuracy, which is the **Gradient Boost** algorithm that has the highest value.

### Forecasting

At this stage, I will attempt to predict using the algorithm we chose above, namely Gradient Boost, over the next 30 days. The following is the predicted future prices for the next 30 days in Table 3, which has been predicted using the Gradient Boost algorithm that we selected as the most optimal.

| Index | Close | Forecast          |
|-------|-------|-------------------|
| 2022-09-26 00:00:00 | 264.0 | NaN               |
| 2022-09-27 00:00:00 | 262.0 | NaN               |
| 2022-09-28 00:00:00 | 264.0 | NaN               |
| 2022-09-29 00:00:00 | 260.0 | NaN               |
| 2022-09-30 00:00:00 | 256.0 | NaN               |
| 0     | NaN   | 847.0             |
| 1     | NaN   | 847.0             |
| 2     | NaN   | 847.0             |
| 3     | NaN   | 847.0             |
| 4     | NaN   | 847.0             |
| 5     | NaN   | 847.0             |
| 6     | NaN   | 847.0             |
| 7     | NaN   | 847.0             |
| 8     | NaN   | 847.0             |
| 9     | NaN   | 847.0             |
| 10    | NaN   | 847.0             |
| 11    | NaN   | 847.0             |
| 12    | NaN   | 847.0             |
| 13    | NaN   | 847.0             |
| 14    | NaN   | 847.0             |
| 15    | NaN   | 847.0             |
| 16    | NaN   | 847.0             |
| 17    | NaN   | 847.0             |
| 18    | NaN   | 847.0             |
| 19    | NaN   | 847.0             |
| 20    | NaN   | 847.0             |
| 21    | NaN   | 847.0             |
| 22    | NaN   | 847.0             |
| 23    | NaN   | 847.0             |
| 24    | NaN   | 848.67            |
| 25    | NaN   | 847.0             |
| 26    | NaN   | 847.0             |
| 27    | NaN   | 847.0             |
| 28    | NaN   | 847.0             |
| 29    | NaN   | 847.0             |

**Table 3. Forecasting**

Table 3 shows the predictions made using **Gradient Boost**, which we selected as the most optimal algorithm. It provides the forecast for the next 30 days.

### References
* Adipta Martulandi (Oct 6, 2019). Tuning Hyperparameters Logistic Regression Using Grid Search #UcupStory, from [Medium](https://medium.com/@adiptamartulandi/tuning-hyperparameters-logistic-regression-menggunakan-grid-search-ucupstory-fb1ab9db082a).
* Mekari (2022). Understanding Forecasting Methods for Your Business Needs from [Jurnal](https://www.jurnal.id/id/blog/mengenal-metode-forecasting-untuk-kepentingan-bisnis-anda/).
* Fakultas Hukum Universitas Medan Area (June 15, 2020). Database Normalization from [Hukum UMA](https://hukum.uma.ac.id/2022/06/15/normalisasi-database/#:~:text=Atau%20pengertian%20singkatny%2C%20Normalisasi%20Databse,database%20yang%20dibuat%20berkualitas%20baik).
* Tom Sharp (Mar 4, 2020). An Introduction to Support Vector Regression (SVR) from [Towards Data Science](https://towardsdatascience.com/an-introduction-to-support-vector-regression-svr-a3ebc1672c2).
* Abdul Muiz Khalimi (January, 2021). How to Calculate RMSE, MSE, MAPE, and MAE with Excel from [Pengalaman Edukasi](https://www.pengalaman-edukasi.com/2021/01/cara-menghitung-rmse-root-mean-square.html).
* GeeksForGeeks (Sep 2, 2020). ML – Gradient Boosting from [GeeksForGeeks](https://www.geeksforgeeks.org/ml-gradient-boosting/).

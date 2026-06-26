# Shipment Delivery Performance Analysis & On-Time Delivery Prediction

## Project Overview

This project is an end-to-end logistics analytics project focused on analysing shipment delivery performance and predicting whether a shipment will reach the customer on time.

The main objective of this project is to understand the key factors that affect delivery success, such as shipment mode, warehouse block, product weight, product importance, customer care calls, product cost, discount offered, and customer rating.

In logistics and e-commerce businesses, on-time delivery plays a very important role in customer satisfaction. Delayed deliveries can increase customer complaints, reduce trust, and affect the overall reputation of an organisation. This project uses data analytics and machine learning to convert raw shipment data into meaningful business insights that can help an organisation improve delivery planning and reduce delay risks.

---

## Business Problem

Many logistics and e-commerce organisations handle thousands of shipments every day. However, not every shipment reaches the customer on time. Delivery delays can happen due to multiple reasons such as product weight, warehouse handling, shipment mode, customer order priority, or operational inefficiencies.

The business problem addressed in this project is:

**How can shipment data be analysed to identify the main factors behind delivery delays and support better logistics decision-making?**

This project helps answer important business questions such as:

* Which shipment mode performs better for on-time deliveries?
* Which warehouse block handles deliveries more efficiently?
* Are heavier products more likely to be delayed?
* Does product importance affect delivery performance?
* Are discounts connected with delayed deliveries?
* Do customer care calls increase for certain shipment types?
* Can machine learning help predict whether a shipment will reach on time?

---

## Why This Project Matters

This project is not only about creating charts. The goal is to show how data can help an organisation move from reactive delivery management to proactive delivery planning.

Without data analysis, a company may only know that deliveries are delayed after customers complain. With this type of analysis, the organisation can identify delay patterns earlier and take action before the customer experience is affected.

This project can help an organisation:

* Identify high-risk shipment categories
* Improve warehouse performance monitoring
* Choose better shipment modes
* Reduce avoidable delivery delays
* Improve customer satisfaction
* Reduce repeated customer care calls
* Support logistics managers with data-driven decisions
* Build a foundation for automated delivery delay prediction

---

## Dataset Description

The dataset contains shipment-level records. Each row represents one shipment order.

### Dataset Size

* Total records: 10,999
* Total columns: 12
* Data type: Structured tabular data
* Target variable: `Reached.on.Time_Y.N`

### Target Variable

```text
Reached.on.Time_Y.N
```

| Value | Meaning                  |
| ----- | ------------------------ |
| 1     | Shipment reached on time |
| 0     | Shipment was delayed     |

### Key Features

| Column                | Description                                           |
| --------------------- | ----------------------------------------------------- |
| `ID`                  | Unique shipment ID                                    |
| `Warehouse_block`     | Warehouse block from which the product was shipped    |
| `Mode_of_Shipment`    | Shipment mode such as Ship, Flight, or Road           |
| `Customer_care_calls` | Number of calls made by the customer to customer care |
| `Customer_rating`     | Rating given by the customer                          |
| `Cost_of_the_Product` | Cost of the product being shipped                     |
| `Prior_purchases`     | Number of previous purchases made by the customer     |
| `Product_importance`  | Importance level of the product: low, medium, or high |
| `Gender`              | Customer gender                                       |
| `Discount_offered`    | Discount offered on the product                       |
| `Weight_in_gms`       | Product weight in grams                               |
| `Reached.on.Time_Y.N` | Delivery status                                       |

---

## Tools and Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Jupyter Notebook / Google Colab

---

## Project Workflow

The project followed a complete data analytics workflow:

1. Data collection
2. Data loading
3. Data inspection
4. Missing value checking
5. Duplicate value checking
6. Data cleaning
7. Feature engineering
8. Exploratory data analysis
9. Data visualisation
10. Grouped business analysis
11. Correlation analysis
12. Machine learning model building
13. Model evaluation
14. Business insights
15. Recommendations for organisation improvement

---

## Data Cleaning and Preparation

The dataset was first loaded using Pandas. After loading the data, basic checks were performed to understand the structure of the dataset.

The following checks were performed:

* Checked the first few rows using `.head()`
* Checked total rows and columns using `.shape`
* Checked column data types using `.info()`
* Checked missing values using `.isnull().sum()`
* Checked duplicate records
* Reviewed numerical and categorical columns
* Prepared the dataset for visual analysis and machine learning

### Feature Engineering

A new feature was created by converting product weight from grams to kilograms.

```text
Weight_in_kgs = Weight_in_gms / 1000
```

A weight category column was also created to analyse delivery performance across different product weight ranges.

Example weight categories:

* 0-2 kg
* 2-4 kg
* 4-6 kg
* 6-8 kg
* 8-10 kg
* 10 kg+

This helped make the analysis easier to understand from a business point of view.

---

## Exploratory Data Analysis

Exploratory Data Analysis was performed to identify patterns in delivery performance. The analysis focused on shipment mode, product weight, warehouse block, customer behaviour, discount patterns, and delivery status.

---

## 1. Shipment Mode vs Delivery Status

This analysis compares delivery performance across different shipment modes such as Ship, Flight, and Road.

![Shipment Mode vs Delivery Status](screenshots/01_mode_vs_delivery_status.png)

### Business Insight

Shipment mode plays an important role in delivery performance. By comparing on-time and delayed deliveries across different shipment modes, an organisation can understand which shipment methods are more reliable and which methods require closer monitoring.

### How This Helps an Organisation

This analysis can help the organisation:

* Select better shipment modes for urgent orders
* Monitor shipment methods with higher delay risk
* Improve delivery planning based on past shipment performance
* Reduce delays caused by poor shipment mode selection

### Business Value

Instead of choosing shipment methods only based on routine or assumption, the organisation can use historical data to make better shipment mode decisions.

---

## 2. Product Weight vs Delivery Status

This analysis checks whether product weight has an impact on delivery delays.

![Product Weight vs Delivery Status](screenshots/02_weight_vs_delivery_status.png)

### Business Insight

Heavier products showed a stronger delay pattern compared with lighter products. This suggests that weight can be an important factor in delivery performance.

Heavy products may require more handling time, better packaging, more loading effort, or specific transport planning. If these factors are not managed properly, delivery delays can increase.

### How This Helps an Organisation

This analysis can help the organisation:

* Identify heavy shipments as high-risk deliveries
* Plan heavy product dispatch earlier
* Assign better handling resources for heavier items
* Use faster shipment methods for high-priority heavy products
* Improve warehouse loading and dispatch planning

### Business Value

The organisation can reduce avoidable delays by treating heavy products as a special shipment category that requires additional planning.

---

## 3. Warehouse Block Delivery Performance

This analysis compares delivery performance across different warehouse blocks.

![Warehouse Delivery Status](screenshots/03_warehouse_delivery_status.png)

### Business Insight

Warehouse performance analysis helps identify which warehouse blocks are handling shipments more efficiently and which blocks may need process improvement.

Some warehouse blocks may have higher shipment volume, while others may have better on-time delivery performance. Therefore, warehouse performance should be reviewed using both total shipment count and delivery percentage.

### How This Helps an Organisation

This analysis can help the organisation:

* Compare warehouse block performance
* Identify warehouse blocks with higher delay counts
* Improve dispatch coordination
* Allocate staff and resources more effectively
* Replicate successful warehouse practices across other blocks

### Business Value

The organisation can improve operational efficiency by identifying performance gaps between warehouse blocks and taking corrective action.

---

## 4. Warehouse Block and Shipment Mode Heatmap

This heatmap shows how shipment modes are used across warehouse blocks for on-time deliveries.

![Warehouse Mode Heatmap](screenshots/04_warehouse_mode_heatmap.png)

### Business Insight

The heatmap provides a clear view of how warehouse blocks and shipment modes work together. It helps identify which combinations are more common for on-time deliveries.

This type of analysis is useful because delivery performance is not affected by only one factor. It can depend on the combination of warehouse block, shipment mode, product type, and operational process.

### How This Helps an Organisation

This analysis can help the organisation:

* Understand which warehouse-shipment combinations perform better
* Identify best-performing delivery patterns
* Improve shipment allocation strategies
* Use successful warehouse-shipment combinations for future planning
* Detect underperforming shipment routes or methods

### Business Value

The organisation can make more informed logistics decisions by understanding the relationship between warehouse operations and shipment methods.

---

## 5. Correlation Analysis

A correlation matrix was created to understand relationships between numerical features.

![Correlation Matrix](screenshots/05_correlation_matrix.png)

### Business Insight

Correlation analysis helps identify relationships between numerical variables such as:

* Product cost
* Discount offered
* Product weight
* Customer care calls
* Customer rating
* Prior purchases
* Delivery status

This helps understand which variables may influence each other and which features may be useful for further modelling.

### How This Helps an Organisation

This analysis can help the organisation:

* Understand relationships between shipment features
* Identify possible factors connected with delivery delays
* Select useful variables for machine learning models
* Support future advanced analysis and prediction

### Business Value

Correlation analysis helps the organisation move from basic reporting to deeper analytical understanding.

---

## 6. Machine Learning: On-Time Delivery Prediction

A machine learning model was developed to predict whether a shipment would reach on time or be delayed.

The target variable used for prediction was:

```text
Reached.on.Time_Y.N
```

### Model Used

```text
Support Vector Machine Classifier
```

### Model Purpose

The purpose of the model is to predict shipment delivery status based on available shipment features.

This type of model can help an organisation identify shipments that may be at risk of delay before the delay actually happens.

![SVM Confusion Matrix](screenshots/06_svm_confusion_matrix.png)

### Business Insight

Machine learning can support proactive delivery management. Instead of waiting for delays to happen, the organisation can use shipment data to identify delay risk earlier.

### How This Helps an Organisation

This model can help the organisation:

* Predict whether a shipment may be delayed
* Identify risky shipments before dispatch
* Prioritise important shipments
* Improve customer communication
* Reduce last-minute delivery issues
* Support automated logistics monitoring

### Business Value

A delivery prediction model can help the organisation shift from reactive problem solving to proactive delay prevention.

---

## Model Evaluation

The machine learning model was evaluated using classification metrics.

Important evaluation metrics include:

| Metric           | Meaning                                            |
| ---------------- | -------------------------------------------------- |
| Accuracy         | Overall percentage of correct predictions          |
| Precision        | How many predicted positives were actually correct |
| Recall           | How well the model identified actual cases         |
| F1-score         | Balance between precision and recall               |
| Confusion Matrix | Comparison of correct and incorrect predictions    |

### Note

The model should be considered a baseline model. It gives a starting point for prediction, but the performance can be improved further by testing multiple algorithms, tuning hyperparameters, and adding more useful features.

---

## Key Findings

### 1. Shipment mode affects delivery performance

The analysis showed that delivery performance varies across shipment modes. This means shipment mode should be considered carefully when planning deliveries.

### 2. Product weight is an important delay factor

Heavier products showed stronger delay patterns. This suggests that heavy products may require special handling, better planning, or priority allocation.

### 3. Warehouse performance can be compared using data

Warehouse block analysis helps identify which blocks handle shipments efficiently and which areas may need improvement.

### 4. Warehouse and shipment mode combinations matter

The heatmap showed that delivery performance can be better understood by analysing warehouse block and shipment mode together.

### 5. Customer care activity can indicate delivery concerns

Customer care calls may be connected with product value, delivery concerns, or customer expectations. This can help organisations improve proactive communication.

### 6. Machine learning can support delivery risk prediction

The baseline SVM model shows that shipment data can be used to predict delivery status and support early delay identification.

---

## Business Impact

This project provides practical business value for logistics and e-commerce organisations.

The analysis can help an organisation improve delivery operations in the following ways:

| Business Area           | How This Project Helps                               |
| ----------------------- | ---------------------------------------------------- |
| Delivery Planning       | Identifies factors connected with delays             |
| Warehouse Operations    | Compares warehouse block performance                 |
| Shipment Mode Selection | Helps choose better shipment methods                 |
| Heavy Product Handling  | Highlights delay risks for heavier products          |
| Customer Experience     | Supports proactive communication for risky shipments |
| Management Decisions    | Provides data-driven insights for logistics planning |
| Machine Learning        | Builds a foundation for automated delay prediction   |

---

## Expected Organisational Benefits

If this type of analysis is applied to real company shipment data, it can help the organisation:

* Reduce avoidable delivery delays
* Improve warehouse efficiency
* Identify high-risk shipments earlier
* Improve shipment mode planning
* Reduce customer complaints
* Improve customer satisfaction
* Support better resource allocation
* Improve operational decision-making
* Build a foundation for predictive logistics analytics

---

## Before and After Analysis

| Before Analysis                                     | After Analysis                                |
| --------------------------------------------------- | --------------------------------------------- |
| Delay reasons are unclear                           | Delay patterns can be identified using data   |
| Warehouse performance is not clearly compared       | Warehouse blocks can be compared separately   |
| Shipment mode decisions may be assumption-based     | Shipment modes can be analysed using evidence |
| Heavy shipment delays may go unnoticed              | Heavy products can be flagged as higher risk  |
| Customer complaints are handled after delays happen | Delay risk can be identified earlier          |
| Managers depend on manual judgement                 | Managers can use data-driven insights         |

---

## Practical Business Example

If an organisation identifies that heavier products are more likely to be delayed, it can create a special handling rule for those shipments.

For example:

* Products above a certain weight can be dispatched earlier
* High-priority heavy products can be assigned faster shipment modes
* Warehouses with higher delay rates can be reviewed
* Customers can receive early tracking updates
* Risky shipments can be monitored before delivery issues happen

This shows how simple shipment data can be converted into practical business actions.

---

## Recommendations

Based on the analysis, the following recommendations can help improve delivery performance:

1. Monitor heavy shipments separately because they may have higher delay risk.
2. Compare warehouse blocks regularly using on-time delivery percentage.
3. Use shipment mode analysis to select better delivery methods.
4. Provide proactive updates to customers for shipments with delay risk.
5. Give special priority to high-importance products.
6. Review discount-heavy orders because they may be linked with delayed delivery patterns.
7. Use machine learning models to identify risky shipments before dispatch.
8. Collect additional data such as dispatch date, delivery date, distance, location, carrier, and shipping cost.

---

## Limitations

The dataset has some limitations:

* It does not include actual dispatch dates.
* It does not include actual delivery dates.
* It does not include delivery distance.
* It does not include customer location.
* It does not include shipping cost.
* It does not show how many days late a shipment was.
* The delivery result is only binary: on time or delayed.
* The model performance is limited by the available features.

These limitations mean that the analysis gives useful patterns, but more detailed operational data would improve the accuracy and business value of the project.

---

## Future Improvements

This project can be improved further by adding more advanced analytics and machine learning techniques.

Future improvements include:

* Testing Logistic Regression, Random Forest, XGBoost, and Gradient Boosting models
* Comparing models using accuracy, precision, recall, F1-score, and ROC-AUC
* Performing hyperparameter tuning
* Adding feature importance analysis
* Creating a Power BI or Tableau dashboard
* Adding delivery date and dispatch date analysis
* Adding route, region, distance, and carrier-level information
* Building a real-time delay risk prediction system
* Deploying the model as a simple web application

---

## Repository Structure

```text
shipment-delivery-performance-analysis/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── data/
│   ├── raw/
│   └── processed/
│
├── notebooks/
│   └── Shipping_Analysis.ipynb
│
├── reports/
│   └── Shipment_Delivery_Performance_Report.pdf
│
├── screenshots/
│   ├── 01_mode_vs_delivery_status.png
│   ├── 02_weight_vs_delivery_status.png
│   ├── 03_warehouse_delivery_status.png
│   ├── 04_warehouse_mode_heatmap.png
│   ├── 05_correlation_matrix.png
│   └── 06_svm_confusion_matrix.png
│
└── src/
    └── future reusable scripts
```

---

## How to Run This Project

### 1. Clone the repository

```bash
git clone https://github.com/your-username/shipment-delivery-performance-analysis.git
```

### 2. Open the project folder

```bash
cd shipment-delivery-performance-analysis
```

### 3. Install required libraries

```bash
pip install -r requirements.txt
```

### 4. Open the notebook

```bash
jupyter notebook notebooks/Shipping_Analysis.ipynb
```

### 5. Run all cells

Run all notebook cells to reproduce the data cleaning, visualisations, analysis, and machine learning model.

---

## Requirements

```text
pandas
numpy
matplotlib
seaborn
scikit-learn
jupyter
```

---

## Skills Demonstrated

This project demonstrates the following skills:

* Data cleaning
* Data preprocessing
* Exploratory data analysis
* Feature engineering
* Data visualisation
* Business problem solving
* Logistics analytics
* Grouped analysis
* Correlation analysis
* Classification modelling
* Model evaluation
* Business insight generation
* Data-driven recommendation writing

---

## Conclusion

This project demonstrates how data analytics can be used to improve shipment delivery performance in a logistics or e-commerce organisation.

By analysing shipment mode, warehouse block, product weight, discount offered, customer care calls, and delivery status, the project identifies patterns that can help organisations understand why delays happen and how they can reduce delay risk.

The project also includes a baseline machine learning model for on-time delivery prediction. This shows how organisations can use historical shipment data to identify risky deliveries earlier and support better planning.

Overall, this project shows how raw shipment data can be transformed into meaningful insights that support better logistics decisions, improved warehouse performance, reduced delivery delays, and better customer satisfaction.

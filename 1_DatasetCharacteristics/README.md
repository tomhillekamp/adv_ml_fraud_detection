# Dataset Characteristics

**[Notebook](exploratory_data_analysis.ipynb)**

## Dataset Information
From the challange description: 
> The aim of our challenge is to find the best way to process and analyse basket data from one of our retailer partners in order to detect fraud cases. Using these basket data, fraudulent customers should be detected, to be then refused in the future.

### Dataset Source
- **Dataset Link:** [Link](/data/) from https://challengedata.ens.fr/challenges/104
- **Dataset Owner/Contact:**  BNP Paribas PF

### Dataset Characteristics
- **Number of Observations:** 92790
- **Number of Features:** 146

### Target Variable/Label
- **Label Name:** fraud_flag
- **Label Type:** Binary Classification
- **Label Description:** The label represents whether a basket is in risk of fraud (1) or not (0)
- **Label Values:** 0 = no fraud, 1 = fraud
- **Label Distribution:** As with most fraud detection tasks, the dataset is very imbalanced. Non-fraud samples: 91471 and fraud samples: 1319.

### Feature Description
[Provide a brief description of each feature or group of features in your dataset. If you have many features, group them logically and describe each group. Include information about data types, ranges, and what each feature represents.]

 - **Feature 1 (ID):** Unique Identifier (Num)
- **Feature Group (item): 24 columns**
    - **Feature (item1 to item24):** Goods category (Char)
- **Feature Group (cash_price): 24 columns**
    - **Feature (cash_price1 to cash_price24):** Cash price for item 1 to item 24 (Num)
- **Feature Group (make): 24 columns**
    - **Feature (make1 to make24):** Manufacturer for item 1 to item 24 (Char)
- **Feature Group (model): 24 columns**
    - **Feature (model1 to model24):** Model description for item 1 to item 24 (Char)
- **Feature Group (goods_code): 24 columns**
    - **Feature (goods_code1  to goods_code24):** Retailers code for item 1 to item 24 (Num)
- **Feature Group (Nbr_of_prod_purchas): 24 columns**
    - **Feature (Nbr_of_prod_purchas1 to Nbr_of_prod_purchas24):** Number of products for each item1 to item24 (Num)
 - **Feature 146 (Nb_of_items):** Total Number of items (Num)


## Exploratory Data Analysis

The exploratory data analysis is conducted in the [exploratory_data_analysis.ipynb](exploratory_data_analysis.ipynb) notebook, which includes:

- Data loading and initial inspection
- Statistical summaries and distributions
- Missing value analysis
- Feature correlation analysis
- Data visualization and insights
- Data quality assessment

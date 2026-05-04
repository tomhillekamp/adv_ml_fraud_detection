# Literature Review

Approaches or solutions that have been tried before on similar projects.

**Summary of Each Work**:

- **Source 1**: [A numeric-based machine learning design for detecting organized retail fraud in digital marketplaces]

  - **[Link](https://www.nature.com/articles/s41598-023-38304-5)**
  - **Objective**: A scalable machine learning strategy for detecting fraud
  - **Methods**: 4 distinct experiments to identify best preprocessing and detection model (with and without data asymmetry handling). Feature engineering, e.g. one-hot encoding of categorical variables. For data imbalance, they use SMOTE, for example. They use SHAP as a model explanation technique.
  - **Outcomes**: The data-level approach to rebalancing classes outperforms the algorithmic approach, the choice of potential features has to be carefully made, the imbalance between classes has to be addressed. For unbalanced data, a combined approach ("stacked generalization") worked best.
  - **Relation to the Project**: We have to rebalance our data, engineer proper features

- **Source 2**: [A Comprehensive Survey on Imbalanced Data
Learning]

  - **[Link](https://arxiv.org/pdf/2502.08960)**
  - **Objective**: Overview of techniques to handle imbalanced datasets (typical in fraud detection)
  - **Methods**: Systematic analysis across four distinct categories: data re-balancing, feature representation, training strategy, and ensemble learning.
  - **Outcomes**: Data rebalancing: e.g. down sampling, generative methods (e.g. SMOTE) or hybrid methods. Feature representation: e.g. cost-sensitive learning, focal loss (capture the class imbalance when calculating loss)
  - **Relation to the Project**: As our dataset is also very imbalanced, we learned some possible techniques to handle that

- **Source 3**: [Fraud Detection Models and their Explanations for a Buy-Now-Pay-Later Application]

  - **[Link](https://dl.acm.org/doi/fullHtml/10.1145/3654522.3654588)**
  - **Objective**: Creating fraud detection models for a "buy now, pay later" service 
  - **Methods**: Training different models on a company dataset. After feature engineering, the models are built by feeding the training data to four well-known algorithms, logistic regression, decision trees, random forest and gradient boosting algorithms. They used explainable AI to understand what features are important. Used downsampling and SMOTE to handle data imbalance.
  - **Outcomes**: Random forrest performed the best. Use SHAP for explainable AI (detect key features). Create new features from the data, e.g. aggregates.
  - **Relation to the Project**: We can use similar techniques to handle data imbalance, create similar new features.

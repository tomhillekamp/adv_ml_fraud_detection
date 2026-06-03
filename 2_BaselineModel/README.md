# Baseline Model

**[Notebook](baseline_model.ipynb)**

## Baseline Model Results

### Model Selection
- **Baseline Model Type:** Simple Neural Network with Linear Layers, ReLU and Dropout
- **Rationale:** Similar to classification layers in a potential future model 

```
model = nn.Sequential(
            nn.Linear(N_INPUT_FEATURES, 16), 
            nn.ReLU(),
            nn.Linear(16, 8), 
            nn.ReLU(),
            nn.Dropout(DROPOUT_RATE),
            nn.Linear(8, 1),
        )
```

### Model Performance
- **Evaluation Metric:** BCEWithLogitsLoss, PR-AUC
- **Performance Score:** 0.0510 PR-AUC (Best Score)
- **Cross-Validation Score:**

    - **Fold 1/5**
        Fold 1 Val PR-AUC: 0.0464

    - **Fold 2/5**
        Fold 2 Val PR-AUC: 0.0418

    - **Fold 3/5**
        Fold 3 Val PR-AUC: 0.0595

    - **Fold 4/5**
        Fold 4 Val PR-AUC: 0.0571

    - **Fold 5/5**
        Fold 5 Val PR-AUC: 0.0669

    **++ Mean Val PR-AUC: 0.0543 (+/- 0.0091) ++**

    **++ Test Set (split from training data) PR-AUC of best baseline model: 0.0510 ++**
    **++ Test Set (public leaderboard) PR-AUC of best baseline model:  ++**

### Evaluation Methodology
- **Data Split:** Train/Validation/Test - 60/20/20
- **Evaluation Metrics:**
    - PR-AUC: This metric is very useful for properly evaluating a model’s performance on the minority class in severely imbalanced classification problems.
    - BCEWithLogitsLoss: used in binary classification problems

### Metric Practical Relevance
The higher the PR-AUC, the better the model is at correctly detecting the minority class, in our case the fraudulent basket samples.

For comparison, from the Challenge Data description:
> Benchmark 1: PR-AUC = 0,017. This first benchmark is a naive one and is based on a baseline model which randomly predicts probabilities between 0 and 1.

> Benchmark 2: PR-AUC = 0,14. This second benchmark is based on our current solution where several pre-processing steps are applied, and a fine-tuned Machine Learning model is used to predict fraud risk.

**--> Our baseline model falls inbetween these reference values.**

## Next Steps
This baseline model serves as a reference point for evaluating more sophisticated models in the [Model Definition and Evaluation](../3_Model/README.md) phase.

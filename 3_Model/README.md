# Model Definition and Evaluation

If you look at the folders in this directory, you see 5 different directories/steps we have taken after creating the baseline model. This is what we have done in each of these directories:

1. **EmbeddingsModel**
    - We build upon the baseline model and created a model that is trained on embeddings of the categorical columns and aggregated numerical features 
2. **Hyperparameter Optimization**
    - We tried to improve the performance of the embedding model by running a hyperparameter optimization using Optuna. However, the best parameters did not improve the results much -> from around 0.16 PR AUC to 0.1727 PR AUC on the validation set.
3. **Feature Engineering**
    - As the hyperparameter optimization did not result in a huge improvement and we probably needed larger changes, we played around with different new numerical features or other ways to combine the categorical features in the embeddings. However, this also did not result in a noticeable improvement. But we noticed that the embeddings were driving factor as the embeddings models PR-AUC ony dropped slightly after removing the numerical input features.
    - During the Literature Review, we found studies that had good results by using tree-based algorithms. Therefore, we tried XGBoost on our existing features. This resulted in a better PR-AUC, especially on the public test set on ChallengeData. It jumped from around 0.13 PR-AUC on the public test set to 0.1895 PR-AUC.
    - We also tried an ensemble approach of combining the embeddings model and XGBoost, however, it seemed as if the embeddings model just impaired XGBoost's performance.
4. **Hyperparameter Optimization: XGBoost**
    - As XGBoost provided better results, we tried running an Optuna study on the XGBoost model to find optimal parameters. This resulted in a slightly better PR-AUC on the validation set, however, on the public test set it performed slightly worse. Possibly, the parameter space was too large in each of our optuna studies, as they did not result in noticeably better performance.
5. **Oversampling/Undersampling**
    - In the literature review, we also found studies that mentioned oversampling/undersampling to counter the class imbalance in fraud classification tasks. Unfortunately, when trying this on our embeddings model, this also did not result in better performance.

The notebook below (**model_definition_evaluation.ipynb**) summarizes everything: it loads our data, does our feature engineering and preprocessing and at the end loads the best embedding and XGBoost model to run inference on the validation set. The PR-AUC values are compared to the baseline model.

It also links to other important notebooks.

**[Notebook](model_definition_evaluation.ipynb)**

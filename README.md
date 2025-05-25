This project presents a machine learning–driven approach to detecting fraudulent Ethereum transactions using on-chain behavioral data sourced via Kaggle, which can be easily implemented into Glassnode’s existing business model. The broader goal of this work is to contribute to the transparency, security, and regulatory compliance of blockchain ecosystems by leveraging data science tools to flag suspicious activity in real-time.

The dataset contains a wide range of features reflecting Ethereum wallet behavior and transactional activity. Our initial steps involved data cleaning (removal of null entries and redundant columns), exploratory data analysis, and feature selection. Through correlation analysis and visualizations (e.g., distribution plots and heatmaps), we identified features with strong predictive power for the target label FLAG, which indicates whether a transaction was fraudulent or not.

We developed and compared five different classification models: Random Forest, XGBoost, LightGBM, CatBoost, and a stacked ensemble of CatBoost and LightGBM. These models were chosen for their robustness and performance on structured/tabular datasets. Our evaluation focused on multiple key metrics—accuracy, recall, AUC-ROC, and the confusion matrix—to ensure a balanced assessment of model effectiveness, especially considering the need to minimize false negatives in fraud detection.

Here are the summarized results:

•	Random Forest achieved an accuracy of 98.46% and an AUC-ROC of 0.9993, but had slightly lower recall (91.85%).

•	XGBoost and LightGBM both achieved 99.23% accuracy, with XGBoost leading in recall (99.67%) and AUC-ROC (0.9976).

•	CatBoost further improved performance with 99.44% accuracy, 98.15% recall, and an AUC-ROC of 0.9995.

•	The stacked model (CatBoost + LightGBM) yielded the best overall trade-off, achieving 99.44% accuracy, 97.41% recall, and 0.9995 AUC-ROC—showing strong generalization and robustness.

The stacking approach allowed us to harness the strengths of both CatBoost (which handles categorical variables and small datasets well) and LightGBM (known for speed and scalability), leading to a highly effective fraud detection pipeline. Confusion matrices showed minimal false negatives, which is critical in preventing fraudulent activities from going unnoticed.

Future improvements may include:

•	Real-time fraud detection pipelines using streaming data (e.g., via Apache Kafka).

•	Deep learning models for temporal or sequential transaction patterns.

•	Feature engineering using smart contract metadata or gas usage anomalies.

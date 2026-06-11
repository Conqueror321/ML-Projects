# Diabetes Prediction (Pima Indians Diabetes Dataset)

This project predicts whether a patient has diabetes based on medical measurements like glucose level, blood pressure, BMI and age. The data is the Pima Indians Diabetes dataset from Kaggle (https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database) with 768 patients. After cleaning the data (the missing values are hidden as zeros, which took me a while to notice) I trained and compared three models: KNN, Random Forest and Gradient Boosting. The best one (Random Forest) gets about 75% accuracy on the test set, compared to a 65% baseline of always predicting "no diabetes".

## How to run

1. Clone the repo
2. Install the libraries: `pip install -r requirements.txt`
3. Open the notebook: `jupyter notebook DiabetesPrediction.ipynb` and run all the cells

The dataset (diabetes.csv) is already in the repo so there is nothing to download.

## Libraries used

- pandas
- matplotlib
- scikit-learn
- jupyter

## What I learned

The biggest lesson was that missing values aren't always NaN — in this dataset they were stored as zeros and I only noticed because describe() showed a minimum blood pressure of 0. I also saw first hand how much feature scaling matters for KNN (accuracy went from 66% to 75% after scaling) while tree based models don't care about it at all. And accuracy alone can be misleading with imbalanced classes — the confusion matrix showed the model still misses about a third of the actual diabetes cases.

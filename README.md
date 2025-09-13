Premier League Winner Prediction
Project Overview
This project predicts the winner of the Premier League 2023–2024 season using historical performance data scraped from FBref.

The workflow includes:

Web scraping with BeautifulSoup and Pandas

Data cleaning and feature engineering

Training a machine learning model (RandomForest Classifier)

Predicting the next champion

Tech Stack
Python (3.8+)

Libraries: Pandas, BeautifulSoup, scikit-learn, Matplotlib, Joblib

Jupyter Notebook for development and reporting

Project Structure
bash
Copy code
pl-winner/
├─ data/          # scraped CSVs (FBref + Transfermarkt if used)
├─ model/         # trained ML models
├─ notebooks/     # Jupyter notebooks (main analysis and report)
├─ src/           # scraping and data preparation scripts
├─ README.md      # project overview (this file)
└─ requirements.txt
Dataset
Seasons scraped: 2018–2019 to 2023–2024

Features used:

points (last season total)

pos (league position)

gd (goal difference, if available)

market_value_eur (squad market values, optional)

Target variable:

won_next = 1 if the team becomes champion in the following season

won_next = 0 otherwise

Model
Algorithm: RandomForestClassifier (class_weight="balanced")

Evaluation: Stratified 5-fold Cross-Validation (F1-score)

Most important features: Points and League Position

Results
Top 5 Predicted Teams for 2023–2024
Team	Points	Pos	Win Probability
Manchester City	91	1	0.270
Liverpool	82	3	0.105
Arsenal	89	2	0.075
Bournemouth	48	12	0.000
Burnley	24	19	0.000

Prediction: Manchester City most likely to win 2023–2024.

Limitations
Small dataset (only 6 seasons).

Market value data incomplete.

Imbalanced target (only one champion per season).

Future Work
Add more seasons for better training.

Scrape advanced stats (xG, xGA, transfers, average age).

Try other models such as XGBoost or CatBoost.

Handle imbalance with oversampling methods like SMOTE.

References
FBref Premier League Stats

Scikit-learn Documentation



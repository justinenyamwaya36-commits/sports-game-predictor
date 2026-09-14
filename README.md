Game Outcome Predictor
A baseline sports analytics project: predicts whether a team wins a game
based on pre-game team stats (offensive/defensive rating, pace, home court).
Built as a portfolio piece to demonstrate the full pipeline — data → model →
evaluation → interpretation — the same workflow used for real betting-market
and team-analytics models.
Why this project
The goal isn't a fancy model. It's showing you can:
Frame a prediction problem correctly (no data leakage, proper train/test split)
Beat a naive baseline and say by how much
Explain why the model predicts what it predicts (coefficients, not a black box)
Results
Metric
Value
Accuracy
68.8%
Baseline (majority class)
51.2%
ROC AUC
0.746
Log loss
0.592
See feature_importance.png for which stats drive predictions, and
example_predictions.csv for sample outputs.
Files
generate_data.py — builds games.csv. Currently uses synthetic data
(simulated team skill ratings) so the project runs offline with no API keys.
train_model.py — trains a logistic regression classifier, evaluates it,
and saves a feature-importance chart.
games.csv, feature_importance.png, example_predictions.csv — generated outputs.
Running it
Bash
Next steps (how to make this a real project)
Replace generate_data.py with real historical data, for example:
nba_api (free, official NBA stats)
basketball-reference.com (scrape or manually export)
Kaggle sports datasets (search "NBA games" or your sport of choice)
Then try:
Adding more features: rest days, injuries, recent form (last-5-games win %)
A gradient boosting model (XGBoost/LightGBM) as a stronger baseline
Calibrating predicted probabilities against real betting-market odds to see
where the model and the market disagree — that gap is where analytics work
actually gets used in the industry.
Note on scope
This predicts based on team stats already collected before the game — it's a
supervised classification project, not a betting tool. No odds, staking, or
wagering logic is included.

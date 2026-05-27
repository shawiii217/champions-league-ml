⚽ UCL Match Predictor — Arsenal vs PSG
End-to-End Machine Learning System for UEFA Champions League Outcome Prediction
📌 Project Overview
This is a complete, production-grade Machine Learning project that predicts the outcome of a UEFA Champions League match — specifically a hypothetical Arsenal vs PSG UCL Final.
The model does not try to predict the future. Instead, it estimates win probabilities based on:

9 seasons of historical UCL data (2015–2026)
55+ engineered features per match
An ensemble of 5 trained ML models


⚠️ Disclaimer: This is a data science portfolio project. It is not betting advice. Football has inherent randomness that no model can fully capture.


🏆 Final Prediction: Arsenal vs PSG
OutcomeProbability🔴 Arsenal Win~22.2%🟡 Draw~17.4% 🔵 PSG Win~60.4%

Probabilities estimated via Weighted Ensemble of 5 ML models + 1,000,000 Monte Carlo simulations.
🗂️ Project Structure
ucl-match-predictor/
│
├── UCL_Match_Predictor_Arsenal_vs_PSG.ipynb   ← Main notebook (run this)
│
├── outputs/
│   ├── arsenal_vs_psg_prediction.png          ← Final match report card
│   ├── model_evaluation.png                   ← Model comparison dashboard
│   ├── shap_importance.png                    ← Feature importance (SHAP)
│   ├── eda_analysis.png                       ← Exploratory data analysis
│   └── sensitivity_analysis.png              ← Elo sensitivity chart
│
├── ucl_predictor_v1/
│   ├── xgb_model.pkl                          ← Saved XGBoost model
│   ├── scaler.pkl                             ← Feature scaler
│   ├── label_encoder.pkl                      ← Label encoder
│   └── feature_cols.json                      ← Feature list
│
└── README.md
🛠️ Features Engineered (55+ total)
CategoryFeaturesElo RatingsTeam Elo, Elo difference, expected win probabilityTeam Form (Last 5)Win %, draw %, loss %, goals scored/conceded per game, points per gameTeam Form (Last 10)Win %, goals scored/conceded, points per gameAttack / DefensexG for, xG against, shot accuracy, conversion rateUCL HistoryWin rate, goal difference per game, titles won, finals reached, strength scoreHead-to-HeadH2H win %, draw %, last 5 meetings recordMatch ContextIs knockout stage?, Is final?, Season index

🤖 Models Trained
ModelDescriptionLogistic RegressionBaseline probabilistic modelRandom Forest300 trees, depth-controlledGradient BoostingSklearn GBM with subsamplingXGBoostBase + Optuna hyperparameter tuned (30 trials)LightGBMFast gradient boostingWeighted EnsembleFinal model — inverse log-loss weighted average of all 5

📊 Model Performance
ModelAccuracyLog LossAUC (OvR)Logistic Regression~ 42.55% ~1.1518~0.5767Random Forest~42.55%~1.0648~0.6208 Gradient Boosting~39.01%~1.2404 ~0.6238XGBoost (Optimized)~45.39%~1.3364 ~ 0.6066LightGBM~45.39%~ 1.6926~ 0.6260 Weighted Ensemble~45.39%~1.1219~0.6271
🎲 Monte Carlo Simulation
1,000,000 simulations were run with ±5% probability noise to account for model uncertainty.
OutcomeSimulated ProbabilityArsenal Win~22.06Draw~17.19%PSG Win~60.76%

📈 Visualizations Produced

✅ EDA dashboard (result distributions, Elo analysis, xG scatter)
✅ Model evaluation dashboard (confusion matrix, ROC curves, calibration plot)
✅ SHAP feature importance (what the model actually uses to decide)
✅ Final match report card (radar chart, pie chart, scoreline heatmap)
✅ Sensitivity analysis (how Elo changes affect win probability
🚀 How to Run
Option 1: Google Colab (Recommended — no setup needed)

Click the notebook file above: UCL_Match_Predictor_Arsenal_vs_PSG.ipynb
Click "Open in Colab" button at the top
Click Runtime → Run all
That's it! All libraries install automatically.
🔌 Predict Any Match (API Function)
After running the notebook, you can predict any UCL matchup using the built-in function:
pythonpredict_ucl_match(
    team1="Arsenal",
    team2="PSG",
    team1_elo=1835,
    team2_elo=1855,
    is_final=True
)
📦 Tech Stack
ToolPurposePython 3.10+Core languagePandas / NumPyData manipulationScikit-learnML models & evaluationXGBoostGradient boosted treesLightGBMFast gradient boostingSHAPModel explainabilityOptunaHyperparameter optimizationMatplotlib / SeabornStatic visualizationsPlotlyInteractive charts
🔮 Future Improvements

 Replace simulated data with real FBref / football-data.co.uk data
 Add player-level features (key player availability, injuries)
 Implement Elo decay for teams in poor recent form
 Add LSTM/Transformer model for time-series form tracking
 Deploy as a Streamlit web app
 🔮 Future Improvements
👨‍💻 About Me
Shahwaiz — BCA Graduate from Brainware University
Passionate about Data Science, Machine Learning, and Big Data.
Actively looking for Data Analyst / Data Scientist roles.
⚠️ Disclaimer
This project is built for educational and portfolio purposes only. The model estimates probabilities from historical data and statistical patterns. It does not predict real future match outcomes. Football is inherently unpredictable — that's what makes it beautiful.

If you found this useful, consider giving it a ⭐ on GitHub!

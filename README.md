# March Madness 2025 - Machine Learning Predictor

## Project Overview
This project uses machine learning to predict the outcome of matchups in the 2025 NCAA March Madness tournament. We leverage historical game data, team statistics, and ESPN’s Basketball Power Index (BPI) rankings to train a model capable of forecasting game results.

## Dataset
We use the following sources for data:
- **Kaggle Dataset**: [2024 March Madness Statistical Analysis](https://www.kaggle.com/datasets/jonathanpilafas/2024-march-madness-statistical-analysis)
- **ESPN BPI Rankings**: [2025 Team Rankings](https://www.espn.com/mens-college-basketball/bpi)

## Data Preparation
1. **Select Top 64 Teams**: Extract the top 64 teams from ESPN’s BPI rankings for 2025.
2. **Generate Matchups**: Create all possible pairwise matchups (64 × 64 = 4096 rows).
3. **Record Past Match Results**: Identify past games between matched teams and note the winner.
4. **Feature Engineering**:
   - Compute statistical differences between teams for relevant features (e.g., `avg_points_per_game_diff` = Team1’s PPG - Team2’s PPG).
   - Use team-based features such as win percentage, offensive/defensive ratings, and turnover rates.
   - Assign a binary target variable (`Winning Team`).

## Model Training
1. **Split Data**: Divide the dataset into training and testing sets.
2. **Model Selection**: Train classification models such as Logistic Regression, Random Forest, and Gradient Boosting.
3. **Hyperparameter Tuning**: Optimize model parameters using GridSearchCV.
4. **Evaluation**: Assess model performance using accuracy, F1-score, and confusion matrices.

## Predictions & Bracket Simulation
- **Predict Tournament Outcomes**: Use the trained model to forecast winners of matchups.
- **Bracket Simulation (Bonus)**: Randomly generate a bracket and predict each round’s winners up to the championship.

## Requirements
Install the necessary Python libraries:
```bash
pip install pandas numpy scikit-learn beautifulsoup4 requests
```

## Running the Project
1. **Download the Kaggle dataset** and place it in the project folder.
2. **Scrape the ESPN BPI rankings** using `scraper.py` (or manually input rankings).
3. **Run the data preprocessing script** to generate the matchup dataset:
   ```bash
   python preprocess.py
   ```
4. **Train the machine learning model**:
   ```bash
   python train_model.py
   ```
5. **Run predictions on matchups**:
   ```bash
   python predict.py
   ```
6. **(Optional) Generate a full bracket prediction**:
   ```bash
   python simulate_bracket.py
   ```

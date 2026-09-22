# Chess Games EDA & Hypothesis Testing

Exploratory data analysis and statistical hypothesis testing on 20,058 online chess games, exploring behavioral patterns, matchmaking fairness, and skill-related trends.

## Data

[Chess Game Dataset (Lichess)](https://www.kaggle.com/datasets/datasnaek/chess) — 20,058 rated and casual games, 16 fields (ratings, moves, opening info, victory status). No missing values.

## Methods

- Data cleaning & descriptive statistics
- Feature engineering: `rating_difference`, `avg_rating`, `game_type` (Bullet/Blitz/Rapid/Classic, parsed from time control)
- Visualization: matchmaking scatter plots, rating/turns distributions, comparisons by game type and outcome
- Hypothesis testing: Welch's two-sample t-test, difference-in-differences with a permutation test (10,000 iterations)

## Key Findings

- **Underdog effect:** games won by the lower-rated player last longer on average (61.9 vs 57.8 turns, Welch's t-test, p ≈ 1.4×10⁻¹⁶).
- **Grandmaster draw gap:** the length gap between draws and checkmates is significantly larger for lower-rated players than higher-rated ones (DiD ≈ -10.4 turns, permutation test p ≈ 0.0011) — stronger players recognize drawn positions earlier.
- Rated games show much tighter matchmaking (avg. rating gap 154 pts) than casual games (avg. gap 253 pts).
- Rapid and Blitz are the dominant time controls on the platform.

## Tools

Python, pandas, matplotlib, seaborn, scipy, numpy

# NFL Bayesian Hierarchical Model

## Status

This project is archived and no longer maintained. It serves as a demonstration of Bayesian modeling in sports analytics.

## Overview

This project predicts NFL game outcomes using a Bayesian hierarchical model. It involves scraping NFL data, creating a comprehensive dataset, and applying Gibbs sampling in R to forecast the 2025 NFL Wild Card games. The model accounts for team strengths, home-field advantages, and various performance metrics to estimate point differentials and win probabilities.

## Data Collection

Data was collected from NFL play-by-play records for the 2024 regular season, supplemented by historical data from 2014 to 2024. Using Python libraries like `nfl_data_py`, `pandas`, and `numpy`, the data was aggregated to include game statistics such as yards gained, turnovers, expected points added (EPA), win probability added (WPA), and completion percentage over expected (CPOE). Additional metrics, like head-to-head records and recent team performance, were computed to enrich the dataset.

## Dataset

The resulting dataset covers all 2024 regular season games, with over 60 variables per game, including:

- Game identifiers (season, week, teams)
- Offensive and defensive stats (e.g., yards, EPA, WPA)
- Historical performance (e.g., 10-season head-to-head records)
- Contextual data (e.g., betting lines, game conditions) The dataset is saved as a CSV file for use in modeling.

## Model

The Bayesian hierarchical model predicts point differentials (home team points minus away team points) using:

- **Team Strengths**: Modeled with an autoregressive process to capture performance changes over time.
- **Home-Field Advantage**: Team-specific bonuses for home games.
- **Covariates**: Betting spread, offensive EPA, WPA, CPOE, and recent points scored. The model is implemented in R using Gibbs sampling, with 5,000 iterations and a 1,000-iteration burn-in, to estimate posterior distributions of parameters.

## Results

The model predicted outcomes for six 2025 NFL Wild Card games, achieving 66.67% accuracy (4 out of 6 games correct). Predicted point differentials and home win probabilities were generated, with visualizations showing prediction uncertainty. Some extreme predictions suggest potential areas for model refinement, such as scaling covariates or adding defensive metrics.

## Usage

1. **Data Scraping**: Run the provided Python notebook to collect and process NFL data.
2. **Model Implementation**: Execute the R Markdown file to fit the model and generate predictions. Ensure all dependencies are installed before running.

## Dependencies

- **Python**: `nfl_data_py`, `pandas`, `numpy`
- **R**: `tidyverse` (additional packages may be required)
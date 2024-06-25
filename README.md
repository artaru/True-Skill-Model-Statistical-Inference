### This project explores Bayesian approaches to player skill modeling using the TrueSkill model. The TrueSkill model is a Bayesian ranking system used to predict the relative skill levels of players based on game outcomes. The key components of this project are:

## Model Definition and Prior:

Each player has a true, but unknown skill level.
The prior distribution for each player's skill is standard normal, indicating independence and equal initial skill levels.
## Likelihood Function:

For each game, the likelihood of a player beating another is modeled based on their skill difference, using a logistic function.
## Stochastic Variational Inference:

Variational inference is employed to approximate posterior distributions of player skills using gradient-based optimization.
The Evidence Lower Bound (ELBO) is maximized to approximate the joint posterior over player skills.
## Real Data Application:

The model is applied to real-world chess game data, involving 2546 games among 1434 players.
The dataset includes player names and game outcomes, used to fit the model and infer skill levels.

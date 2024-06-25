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


# Part 1: TrueSkill Model and Probabilistic Inference
In the first part of this project, we delve into the TrueSkill model, a Bayesian framework for ranking players based on their performance in games. The TrueSkill model assumes each player has a true but unknown skill, modeled as a random variable. The primary components include:

Prior Distribution: Each player's skill is assumed to follow a standard normal distribution, indicating our initial belief about their skill level.
Likelihood Function: The likelihood of a player winning a game depends on the difference in skill levels between two players. A logistic function is used to model this probability.
Posterior Distribution: By combining the prior and the likelihood, we derive the posterior distribution, which updates our beliefs about the players' skills based on observed game outcomes.
We define key functions for calculating the log-prior, log-likelihood, and posterior distributions. These functions enable us to understand the probabilistic relationships between players' skills and game outcomes. Additionally, we visualize the skill distributions and their updates using contour plots.

# Part 2: Stochastic Variational Inference in the TrueSkill Model
The second part focuses on approximate inference using Stochastic Variational Inference (SVI) within the TrueSkill framework. SVI is employed to approximate the posterior distributions of player skills, which are computationally intractable to calculate directly due to the large number of players and games. Key aspects include:

Variational Inference: We approximate the true posterior distribution with a simpler, tractable distribution by optimizing the parameters of this variational distribution to minimize the Kullback-Leibler (KL) divergence from the true posterior.
Evidence Lower Bound (ELBO): We derive the ELBO as the objective function to be maximized during optimization. It serves as a lower bound to the log marginal likelihood of the observed data.
Reparameterization Trick: To efficiently sample from the variational distribution, we use the reparameterization trick, enabling us to perform gradient-based optimization.
Implementation and Optimization: We implement the SVI algorithm, initialize variational parameters, and optimize them to fit the joint distribution of player skills conditioned on observed game outcomes. The optimized variational distribution provides an approximate posterior over all players' skills.
Finally, we apply this methodology to a real-world dataset of chess games, showcasing how the TrueSkill model and SVI can infer player skills from empirical data. We visualize the approximate mean and variance of players' skills, as well as the joint skill distributions for specific player pairs, demonstrating the practical utility of the approach.

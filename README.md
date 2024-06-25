### Bayesian Inference Methods for Skill Estimation in Competitive Games

![image](https://github.com/artaru/True-Skill-Model-Statistical-Inference/assets/79018762/afc2d160-5672-4c86-b567-d15db914f04f)

#### Overview
This project explores two Bayesian inference methods, Hamiltonian Monte Carlo (HMC) and Stochastic Variational Inference (SVI), applied to the TrueSkill model for skill estimation in competitive games. TrueSkill extends traditional rating systems by modeling each player's skill as a latent variable, crucial for predicting game outcomes accurately.

#### Hamiltonian Monte Carlo (HMC) Approach
Hamiltonian Monte Carlo is employed to approximate posterior distributions over player skills conditioned on game outcomes. It leverages gradient-based techniques to sample from complex posterior distributions efficiently.

- **Model Definition:** TrueSkill assumes each player's skill follows a standard normal distribution. The likelihood of one player defeating another is determined by their skill difference, modeled using a logistic function.

- **Implementation:** Functions are implemented to compute the Log Prior (logarithm of the prior distribution for player skills) and Log Likelihood (log-likelihood of game outcomes based on player skills). HMC iteratively refines posterior estimates, visualizing skill distributions before and after observing game results.

- **Visualization:** Plots depict joint distributions of player skills, illustrating changes from prior beliefs to posterior estimates. Real data from chess games validates HMC's effectiveness in estimating player rankings.

#### Stochastic Variational Inference (SVI) Approach
SVI offers a scalable alternative to exact inference and MCMC by optimizing a lower bound on the evidence, using gradient-based methods for parameter updates.

- **Model Specification:** TrueSkill assumes player skills are Gaussian-distributed. SVI approximates the posterior using a diagonal Gaussian variational distribution, facilitating efficient gradient optimization.

- **Implementation:** The repository provides tools to compute the Evidence Lower Bound (ELBO) and optimize variational parameters iteratively using stochastic gradient descent (SGD). This approach is particularly suitable for large datasets, such as extensive records of chess game outcomes.

- **Key Components:** SVI's diagonal covariance matrix simplifies computation but may sacrifice some accuracy compared to MCMC, which ensures exact posterior sampling. Despite this, SVI's scalability makes it preferable for large-scale applications.

#### Conclusion
By comparing HMC and SVI within the TrueSkill framework, this project demonstrates their complementary strengths: HMC for accurate posterior sampling and SVI for scalable inference. Both methods contribute valuable insights into player ranking and skill estimation in competitive games, bridging theoretical Bayesian principles with practical data analysis.

For detailed implementations and results, refer to the project repository and accompanying documentation.

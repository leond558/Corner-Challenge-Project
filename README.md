# Corner-Challenge-Project
Using statistical analysis, python and basic machine learning to develop a model to predict football corners for sports betting. The jupyter notebook contains the code. There is a test and training csv with back data and also a completed spreadsheet.

Two Generalized Linear Models (GLMs) using a negative binomial distribution with a logarithmic link function were fitted to predict home and away corners separately. This bivariate approach yielded models with the lowest relative AIC scores and the best mean squared error. The negative binomial distribution was chosen due to the discrete count nature of corner data and its tendency for overdispersion (variance greater than the mean), making it more appropriate than a Poisson distribution. Visualization techniques such as histograms and QQ plots were employed to validate this assumption.

Feature selection for the model was performed using a Random Forest algorithm to determine feature importance. The Data column was separated into DayOfWeek, Month, and Year entries to explore potential seasonal dependencies in corner counts. Additionally, a PastGoalsAvg feature, representing the historical average goals scored by both teams, was created and proved to be a strong predictor. Categorical data such as seasonal and matchup information were utilized alongside numerical features. The GLM facilitated the combination of multiple data types.

The probability of being under/at/over the supplied line was determined using the predicted mean total corners from the match as the negative binomial parameter. Cumulative Distribution Function (CDF) and Probability Mass Function (PMF) were then employed to calculate the probabilities.

Bets on matches were made based on expected value, with preference given to the bet with the greater expected value. Staking amounts were determined using the Kelly Criterion.

Future Improvements:
Explore alternative modeling techniques such as bivariate Poisson distribution or other advanced discrete distributions.
Experiment with different features and data transformations to enhance model performance.
Consider obtaining additional data/features for improved prediction accuracy.
Verify the correctness of the Kelly Criterion implementation and bankroll calculations.

# A/B Testing: Evaluating a New E-Commerce Recommendation Algorithm

## Overview
This repository explores whether an experimental (simulated) recommendation system increases the proportion of recommended items that customers purchase compared to the existing system. Using an A/B experiment approach, I simulated a scenario with a significant and non-significant improvements. Data is simulated to demonstrate two common experimental outcomes: a result that is statistically significant but below the practical signifance threshold, and a result that fails to reach statistical significance entirely.

## Key Findings
1. **Statistical significance alone is insufficient for adoption decisions.** In the first simulation, the experimental algorithm produced a statistically significant increase in purchase rate, but observed lift (1.64%) fell below the pre-established practical significance threshold of 2.0%. Despite a real effect existing, the business case for adoption was not met, illustrating why effect size and practical thresholds must be defined before analysis begins. 
2. **In the second simulation, the algorithm failed both statistical and practical significance conditions**. The difference in purchase rates was not statistically significant (p = 0.736) and the observed lift was negligible (0.22%), providing no evidence the algorithm outperforms the existing system under either standard.

## Methodology
- **Power analysis**: Conducted using **statsmodels** to determine minimum sample size (n = 2,199 per condition) prior to data collection.
- **Data simulation**: Purchase outcomes were simulated using **NumPy** under two scenarios, one where the effect surpasses a statistical significance threshold, but not a practical significance threshold, and one where the effect surpasses neither.
- **Hypothesis testing**: Two proportion z-test using **statsmodels** to evaluate whether the experimental algorithm significantly increased the proportion of recommended items purchased.
- **Practical significance**: A minimum detectable effect of 2.0% was pre-set as the adoption threshold, independent of statistical significance.

## How to Run
1. Clone the repo
2. Install dependencies from `requirements.txt`
3. Run `ab_testing_practically_nonsignificant.ipynb` to explore a scenario where the experimental algorithm produces a statistically significant result that fails to meet the practical significance threshold for adoption.
4. Run `ab_testing_statistically_nonsignificant.ipynb` to explore a scenario where the algorithm fails to produce a statistically significant result entirely.

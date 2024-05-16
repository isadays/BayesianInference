Main Question Answered:

How well can the model predict the treatment success rate for new TB cases using dimensionality reduction and top contributing features?

1) PCA 
Answer:
The model predicts the treatment success rate for new TB cases with high accuracy and robustness. By applying PCA to reduce dimensionality and focusing on the top contributing features, the model explains, on average, 86.75% of the variance in the target variable across different cross-validation folds, with a consistent performance indicated by a low standard deviation of 0.0225. This demonstrates that the model is both accurate and reliable for predicting the treatment success rate, making it a valuable tool for analyzing and predicting outcomes in TB treatment programs.

Insights:

- Analyzing the top contributing features provides insights into which factors most significantly influence the treatment success rate, helping to inform targeted interventions or further research.
Model Refinement:

- The current model performance can be improved further through hyperparameter tuning and exploring other regression models.

Practical Application:

The high and consistent performance of the model suggests it can be reliably used in practical settings to predict treatment success rates, aiding healthcare providers and policymakers in making informed decisions. By achieving high predictive performance and robustness, the model effectively addresses the main question and provides a solid foundation for further applications and improvements in predicting TB treatment success rates.

- Achievements of the Model:

The model achieved a high R² score on cross-validation, indicating that it explains a significant portion of the variance in the target variable. Mean Cross-validated R² Score: 0.8675, meaning the model, on average, explains 86.75% of the variance in the treatment success rate for new TB cases.

The low standard deviation of the cross-validated R² scores (0.0225) indicates that the model's performance is consistent across different folds, suggesting good generalizability.
Cross-validated R² Scores: [0.9034, 0.8751, 0.8354, 0.8690, 0.8548]
Effective Dimensionality Reduction:

The model retained essential information while reducing complexity, leading to improved performance.
Number of Components Retained: 19, capturing around 95% of the variance.
Identified Key Features: The analysis identified key features that significantly contribute to the variance in the target variable, providing valuable insights for further investigations or decision-making.


2) Bayesian Inference

Parameter Estimates:
Alpha (Intercept):

Mean: 76.493
Standard Deviation (sd): 0.153
Highest Density Interval (hdi_3%, hdi_97%): [76.199, 76.778]
Effective Sample Size (ess_bulk): 2041.0
R-hat: 1.0 ( good convergence)
The intercept (alpha) indicates that the baseline treatment success rate, when all predictors are at their mean values, is approximately 76.5%.

Beta Coefficients (Slope for Each Predictor):

Beta[0] (rep_meth): 0.110 (sd: 0.159, HDI: [-0.183, 0.412])
Beta[1] (new_sp_coh): -0.717 (sd: 0.883, HDI: [-2.342, 0.967])
Beta[2] (new_sp_cur): -0.035 (sd: 0.790, HDI: [-1.607, 1.342])
Beta[3] (new_sp_cmplt): 0.034 (sd: 0.249, HDI: [-0.426, 0.496])
Beta[4] (new_sp_died): -0.423 (sd: 0.521, HDI: [-1.376, 0.574])
Beta[5] (new_sp_fail): 1.536 (sd: 0.352, HDI: [0.883, 2.173])
Beta[6] (new_sp_def): -0.406 (sd: 0.486, HDI: [-1.292, 0.513])
Beta[7] (c_new_sp_tsr): 12.808 (sd: 0.166, HDI: [12.492, 13.114])
Beta[8] (c_ret_tsr): 1.955 (sd: 0.157, HDI: [1.671, 2.253])
The beta coefficients represent the change in the treatment success rate for a one-unit change in the predictor variable. Notably:

c_new_sp_tsr (Beta[7]) has a large positive effect (12.808) on the treatment success rate.
new_sp_fail (Beta[5]) also has a significant positive effect (1.536).

Sigma (Residual Standard Deviation):

Mean: 8.832
Standard Deviation (sd): 0.109
Highest Density Interval (hdi_3%, hdi_97%): [8.618, 9.024]
The sigma value indicates the variability in treatment success rates not explained by the model.

Model Performance Metrics:

Test Set Mean Squared Error (MSE): 84.347
Test Set R^2 Score: 0.687
The model explains approximately 68.7% of the variance in the treatment success rates, indicating a moderate level of predictive power. The MSE indicates the average squared difference between the actual and predicted values.

Credible Intervals:
The credible intervals (HDI) for the beta coefficients provide a range within which the true parameter values lie with a 94% probability. These intervals indicate the uncertainty around the estimated effects of each predictor.

Main Findings:
Significant Predictors:

c_new_sp_tsr (Beta[7]): The large positive coefficient (12.808) and narrow credible interval [12.492, 13.114] indicate that this variable is a strong predictor of treatment success rate. An increase in this predictor significantly increases the success rate.
new_sp_fail (Beta[5]): This predictor also has a notable positive effect on the treatment success rate with a credible interval [0.883, 2.173].
Less Significant Predictors:

new_sp_coh (Beta[1]) and new_sp_cur (Beta[2]): These predictors have wide credible intervals that include zero, suggesting their effects are uncertain and potentially not significant.

Sigma (Residual Variability): The estimated sigma of 8.832 indicates a moderate amount of unexplained variability in the treatment success rates.
R-hat Values: All R-hat values are close to 1, indicating good convergence of the MCMC chains.
Summary:

The Bayesian regression analysis reveals that c_new_sp_tsr and new_sp_fail are significant predictors of the treatment success rate, while other predictors show less certainty in their effects. The model captures a substantial portion of the variance in the data, but there is still room for improvement. The results provide insights into which factors most strongly influence treatment success rates and the associated uncertainties.



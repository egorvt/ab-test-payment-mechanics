**A/B Test: Payment Mechanics Experiment**
==========================================

The A/B test evaluates a new payment mechanism. Group A represents the baseline control flow, and Group B represents the new treatment flow. The stated objective is to determine the viability of a platform-wide rollout based on revenue impact and statistical significance.

**Methodological Assessment**
-----------------------------

The original analytical design contained critical methodological errors. The initial dataset merging excluded non-converting users, artificially inflating average metrics and invalidating the conversion rate. A rigorous evaluation mandates an Intention-to-Treat protocol. All randomized subjects must remain in the dataset to preserve causal integrity.

**Input Data**
--------------

The analysis utilizes four comma-separated value files:

*   groups.csv: Baseline user assignment.
    
*   groups\_add.csv: Supplemental user assignment.
    
*   checks.csv: Transaction records.
    
*   active\_studs.csv: Platform activity logs.
    

**Metrics Analyzed**
--------------------

The evaluation relies on three metrics to isolate acquisition efficiency from transaction magnitude:

*   **Conversion Rate**: The binary probability of transaction execution.
    
*   **ARPPU**: The mean transaction value of converting users.
    
*   **ARPU**: The mean revenue generated across the entire cohort.
    

**Statistical Approach**
------------------------

Revenue distributions consistently exhibit heavy right-skewness. Parametric assumptions are mathematically invalid for this dataset.

*   **Chi-Square Test**: Applied to evaluate frequency discrepancies in the binary conversion rate.
    
*   **Bootstrap Resampling**: Applied to construct empirical distributions for ARPU and ARPPU. This method generates 95% confidence intervals reflecting true variance without relying on theoretical normality.
    

**Conclusions**
---------------

The empirical evidence isolates the financial impact strictly to existing spenders.

The Chi-Square test for conversion rate yields a p-value of 1.0000. The treatment mechanism exerted zero causal influence on user acquisition.

The ARPPU 95% confidence interval spans 68.0671 to 409.2956. The intervention increased the transaction size for users predisposed to convert.

The ARPU 95% confidence interval spans -0.1450 to 3.6256. The revenue gains extracted from the paying subset fail to elevate the average revenue of the entire assigned population.

The intervention does not increase overall average revenue per user. The new payment flow lacks empirical justification for a platform-wide rollout.

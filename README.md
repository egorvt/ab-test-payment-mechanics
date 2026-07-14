A/B Test: Payment Mechanics Experiment
======================================

Project Overview
----------------

This project evaluates the impact of a new payment mechanism on user conversion and revenue generation. The objective is to determine whether the treatment flow yields statistically significant improvements over the baseline control group, providing an evidence-based recommendation regarding a platform-wide rollout.

Data Sources
------------

The analysis synthesizes raw experimental data from the following sources:

*   groups.csv: Baseline user assignment to A/B groups.
    
*   groups\_add.csv: Supplemental user assignments.
    
*   checks.csv: Transaction records during the experimental window.
    
*   active\_studs.csv: Platform activity logs utilized for telemetry validation.
    

Tech Stack
----------

*   **Language**: Python
    
*   **Libraries**: pandas, numpy, scipy.stats, statsmodels
    

Methodology
-----------

The evaluation relies on an Intention-to-Treat protocol, ensuring all randomized subjects remain in the dataset to preserve causal integrity. The analysis evaluates three primary metrics to isolate acquisition efficiency from transaction magnitude:

*   **Conversion Rate**: Evaluated via a Chi-Square Test for Independence to assess the binary probability of transaction execution.
    
*   **ARPPU (Average Revenue Per Paying User)**: Evaluated via Bootstrap Resampling to assess the mean transaction value of converting users without relying on restrictive parametric assumptions.
    
*   **ARPU (Average Revenue Per User)**: Evaluated via Bootstrap Resampling to assess the aggregate financial impact across the entire assigned cohort.
    

Key Findings
------------

*   **Conversion Rate**: The Chi-Square test yielded a p-value of 1.0000, establishing that the new payment flow exerted zero causal influence on user acquisition.
    
*   **ARPPU**: The 95% confidence interval \[68.0671, 409.2956\] strictly excludes zero. The intervention significantly increased the transaction size for users already predisposed to convert.
    
*   **ARPU**: The 95% confidence interval \[-0.1450, 3.6256\] crosses zero. The revenue gains extracted from the paying subset are mathematically insufficient to elevate the average revenue of the entire assigned population.
    

Business Recommendation
-----------------------

The new payment mechanics act strictly as an optimization for existing spenders and fail to expand the broader revenue base. Because the intervention does not increase overall average revenue per user, the new payment flow should not be rolled out if the primary strategic objective is top-line revenue growth across the entire customer base.

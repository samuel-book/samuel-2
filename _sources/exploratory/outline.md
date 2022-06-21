# Outline

The notebooks in this experimental section tackle specific questions that arise during the course of the project. These are often important experiments in understanding model behaviour (often motivated by a 'surprising' result) , but are details not needed in the general narrative of the project.

* *Logistic regression: Understanding hospital one-hot coefficients*: 
    * *Motivation*: We predict thrombolysis use, for any patient, at different hospital by changing the one-hot hospital encoding (while keeping all other patient features unchanged). When we passed a 10K set of patients through all hospitals (by changing the one-hot encoding), we expected that the hospital rank order for the predicted thrombolysis use in that 10K cohort patients would be the same as the rank order of model coefficients for each of the hospital one-hot features. But we did not see exactly the same rank order. This notebook explores (and uncovers) the reason for the different rank orders.
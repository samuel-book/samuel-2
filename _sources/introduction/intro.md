# Introduction to SAMueL-2 (Stroke Audit Machine Learning)

**Use of simulation and machine learning to identify key levers for maximising the disability benefit of intravenous thrombolysis in acute stroke pathways**

```{epigraph}
"Your decision to treat or not treat … That’s the difficult part. That’s the grey area where everyone does a different thing."

-- Stroke Consultant during interviews for SAMueL-1
```

## Summary of research

BACKGROUND AND OVERALL AIM

In England and Wales, 11%-12% of emergency stroke patients receive thrombolysis, significantly below the NHS Long Term Plan target of 20% by 2025. 

The overall aim of SAMUeL-2 is to work with the Sentinel Stroke National Audit Programme (SSNAP) to increase the impact of national audit by providing advanced tools for in-depth comparisons between hospitals, helping to address the gap between actual and achievable thrombolysis use. 

In previous work (SAMueL-1) we have used clinical pathway simulation and machine learning to model stroke pathways to thrombolysis at all (anonymised) hospitals, and to compare decision-making between hospitals. We found that about half of the current inter-hospital variation in thrombolysis use comes from differences in local patient populations and the other half from differences in hospital processes and decision-making. We found that stroke thrombolysis use could be reasonably expected to reach 18%-19% of hospitalised stroke patients. The largest single improvement would come from clinical decision-making at all hospitals being similar to 30 top- ‘benchmark’ hospitals with higher thrombolysis use. The next largest improvement would come from increasing the proportion of stroke patients whose stroke onset time is determined, to a level currently achieved by hospitals achieving upper quartile performance. Finally, speeding the stroke pathway at all hospitals would increase thrombolysis use, but by the smallest margin - although speeding the stroke pathway increases the clinical benefit of thrombolysis for all treated patients.

SPECIFIC OBJECTIVES

Specific objectives are based on feedback received during SAMueL-1, and feedback on the SAMueL-2 bid proposal.

1. Expansion of SAMueL-1 modelling to include: 1) outcome and adverse event prediction at patient-level, 2) inclusion of pre-hospital times in pathway model, 3) use of organisational factors (such as staffing) in predicting use of thrombolysis, and 4) piloting of a model that incorporates use of thrombectomy alongside thrombolysis.

2. Incorporation of health economic outcomes (Quality Adjusted Life Years): These will be adapted from other NIHR projects involving this team that have already developed health economic models for thrombolysis in acute ischaemic stroke.

3. Promote acceptance of the modelling by increased transparency and explainability: 1) make use of Shapley values to show the contribution of individual features to the prediction that the model is making, 2) improved methods for clustering of patients to clarify patterns of differences in clinical decision-making between hospitals and to allow identification of ‘similar hospitals’ (by patient population) for comparison, 3) investigation of bias in model (e.g. accuracy analysis by patient subgroups), 4) generation of dashboards and other interrogative methods.

4. Generation of synthetic data and artificial patient vignettes: 1) build on pilot work already performed for generating synthetic patient-level stroke data that may be shared freely and used for discussion of ’virtual’ patients, 2) automatic generation of artificial clinical vignettes from real or synthetic SSNAP data.

5. Co-production of project outputs with clinicians to promote acceptance and use for local quality improvement: By using both information gathering (through interviews) and intervention refinement (in workshops) we will incrementally modify and improve the content and style of our intervention (SAMueL tool). Working with our Public and Patient Involvement (PPI) group we will also produce key public-facing output.

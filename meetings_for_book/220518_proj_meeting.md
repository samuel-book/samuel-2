# SAMueL2 Kick off meeting (18th May 2022)

## Slide packs:

* General slides: https://github.com/samuel-book/samuel-2/blob/main/meetings_for_book/220518_general_slides.pdf
* Qualitative research slides: https://github.com/samuel-book/samuel-2/blob/main/meetings_for_book/220518_qual_slides.pdf

## Attendees:
* Leon Farmer [LF] – PPI representative
* Kristin Liabo [KL] – PPI researcher
* Mike Allen [MA] – PenCHORD modeller
* Richard Everson [RE] – Professor of Machine Learning
* Anna Laws [AL] – PenCHORD modeller
* Chrissie Walker [CW] – PenCHORD Research and Operations Manager
* Martin James [MJ] – Stroke consultant
* Ken Stein [KS] – Professor of Public Health
* Peter McMeekin [PM] – Health economist
* Tom Monks [TM] – Deputy director of PenCHORD, modeller
* Catherine Pope [CP] – Medical sociologist. Qualitative
* Penny Thompson [PT] – PPI representative
* Kerry Pearn [KP] – PenCHORD modeller (note taker) 

Apologies:
Julia Frost – Qualitative researcher

## Why SAMueL? [MJ]

MJ is the clinical director of SSNAP. SSNAP is a quality improvement project/program for stroke – it aims to increase the use of stroke treatment, improve the speed of treatment and improve the care. SSNAP is in it’s 10th year of prospective national data collection of stroke admissions, and contains 1 milion records in total. 

SAMueL (Stroke Audit Machine Learning) is a reflection of the opportunity of the interaction between ML and big datasets (SSNAP). The population benefits from reperfusion treatment for stroke (using either thrombolysis or thrombectomy - blood clot extraction) is highly time dependant, with patients getting a much better benefit from earlier treatment (due to the brain being very sensitive of being starved by oxygen). The juxtaposition between big data and ML allows us to investigate the real potential for quality improvement in national datasets. This can take big national datasets to a new level by understanding variation between the hospital providers. There is a 5 fold variation in people getting treatment between hospitals, and a 7 fold variation in the population benefit (measured as the number of people that walk out of the hospital without any disability from their stroke).

We want to understand the source of variation between hospitals, and identify key interventions in pathway of care, key steps that might translate into improvements to patients (give treatment more quickly, or to more people).

From clinical point of view, the other key component of this work is the qualitative aspect. How do clinicians respond to receiving feedback about their service. How can this benefit clinical decision making in a patient benefit way.  Where and how can we improve delivery of thrombolysis treatment, so more people can leave hospital without disability from their stroke.

## SAMueL introduction [MA]

There are two videos to introduce the SAMueL project.

* Short (10 min): https://youtu.be/d7Z0dpU3iiM

* Long (45 min): https://youtu.be/6UXdEF9Hrbw

SAMueL-1 project book: https://samuel-book.github.io/samuel-1/
SAMueL-1 summary paper (*Stroke*): https://www.ahajournals.org/doi/10.1161/STROKEAHA.121.038454


## Qualitative research [IL, reporting on behalf of JF]

See attached slides.

Current priority is to plan the qual work and the best way through ethics. This will be a key job for the new SAMueL RF to work on (post-meeting note: Keira Pratt-Boydon joined us at the end of June).

## PPI [LF]

Leon currently establishing the PPI group.

Post-meeting note: The PPI group has been established, and has had its first meeting. It will now be called the Patient and Carer Involvement (PCI) Group to emphasise the contribution of careres.

# Quantitative Research [MA]

Anna Laws joined us at the beginning of May.

The key areas for the quantitative work are:

1. Explainable AI
2. Summarising differences in clinical decision making
3. Predict outcome (as well as give treatment) ML (more detailed outcomes model)
4. Include organisational audit factors (do specialist nurses give thrombolysis more?)
5. Granular outcome (mRS) prediction in pathway simulation model (rather than 
6. Health economics model (PM)
7. Synthetic data to share our models – as is made up data (convince HQIP that we can release this).
8. Production code and prototype web application.

Focus is currently on 1,2 and 3. There will be a more detailed update on Explainable Machine Learning in July, but briefly om machine learning:

* We have re-optimised previous models with the Optuna optimisation library, and have shown that previously used hyper-parameters settings were near-optimal.
* We have added two new model types: XGBoost and LightGBM (both are derivatives of random forest). They do not increase the accuracy of the model, but they may be a benefit when running code on SSNAP servers - shorter run times.
* We have re-engineered the features – this is not to increase the accuracy of the model, but when there’s huge overlap in the features it’s good to simplify the model to make it more explainable. Want to choose the simplest model with maximum accuracy.
* Explainable AI – allows you to peer under bonnet and look at the workings on the model. We have ;looked at SHAP values. SHAP from game theory. How much does each person add/subtracts to the outcome. These offer universal explainability, as can be used for all ML models. SHAP is not the only area for explainable AI, and we will look at others, but they may be the main focus.
* SHAP values do not provide a causal model, but give the reason behind why the model predicted not to give thrombolysis. You start with the base value (n random forest model this is 0.33, and is roughly the proportion of population receive thrombolysis). Then the SHAP values can show the contribution from each feature that moves the value from the base value to the prediction.
* Showing SHAP values to clinicians will be a good basis for starting a discussion. Here is why the model thinks you didn’t give thrombolysis to this patient. Anything ring true/looks odd?









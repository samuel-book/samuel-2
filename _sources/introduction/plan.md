# Research plan

NIHR134326: Stroke Audit Machine Learning (SAMueL-2)

Note: This is a follow-on project to a NIHR HS&DR project (Ref: 17/99/89), referred to here as SAMueL-1. An online book for SAMueL-1 (which includes both summaries and details of work) is available at: https://samuel-book.github.io/samuel-1

(This is Research Plan V3, 20/12/2021)

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

## Background and rationale

### Stroke

Stroke happens when blood flow to an area of the brain has been interrupted, causing cell death [1]. Stroke may be ischaemic, due to an arterial blockage, or haemorrhagic, due to bleeding. Stroke is the main cause of adult-onset long-term disability and a major burden on health and social care services. It was estimated that in 2010, there were 5.9 million deaths and 33 million stroke survivors worldwide [2]. Eighty-five thousand people are hospitalised with stroke each year in England, Wales and Northern Ireland [3]. Over the last 25 years in England stroke has consistently been one of the leading cause of lost disability-adjusted life years, which combine mortality and disability burdens [4].

### Intravenous thrombolysis

Intravenous thrombolysis is a ‘clot-busting’ therapy developed to treat ischaemic stroke by removing or reducing the blood clot obstructing blood flow in the brain. For ischaemic stroke, thrombolysis is an effective but time-critical treatment for the management of acute stroke if given within four and a half hours of stroke onset [5], and is recommended for use in expert guidelines worldwide [6].

### Targets for thrombolysis use and speed

The European Stroke Organisation have promoted a European Stroke Action Plan [7], including a target of at least 15% thrombolysis, with median onset-to-treatment times of <120 minutes, noting that evidence suggests that achieving these targets may be aided by centralisation of stroke services [8,9]. An analysis of the largest randomised trial of thrombolysis concluded that 60% of ischaemic stroke patients arriving within 4 hours of known stroke onset were suitable for thrombolysis [10]. In 2016-18 in England and Wales, about 40% of emergency stroke patients arrived within 4 hours of known stroke onset (data from SAMueL-1). Given that about 85% is stroke is ischaemic, this gives a potential target of 20% thrombolysis.

The 2019 NHS Long Term Plan [11] sets out the ambition of 20% of emergency stroke patients receiving thrombolysis, such that by 2025 England will have amongst the best performance in Europe for delivering thrombolysis. This target is incorporated into the 2021 service specification for the 20 new Integrated Stroke Delivery Networks [12]. Current thrombolysis use in England and Wales is 11-12% on average but ranges from about 2% to 25% between hospitals [3], and has been static at this level for the last 8 years.

The NHS plan for improving stroke care also sets a target that patients should receive thrombolysis within 60 minutes of arrival, but ideally within 20 minutes [12]. Whilst this speed of thrombolysis, called door-to-needle time, provides an ambitious target, it has been shown to be achievable as Helsinki University Central Hospital has reported a median door-to-needle time of 20 minutes, with 94% of patients treated within 60 minutes [13] - a model that has proved rapidly transferable elsewhere [14]. This speed was achieved by innovative solutions like paramedics taking patients straight to the scanner and with thrombolysis delivered close to or in the scanner.

### Clinical audit

Clinical audit seeks to drive quality improvement through the measurement of clinical quality against evidence-based standards [15]. In England and Wales, the Healthcare Quality Improvement Partnership (HQIP) is responsible for commissioning 28 national clinical audits which form the National Clinical Audit and Patient Outcomes Programme. The national audit of stroke is the Sentinel Stroke National Audit Programme (SSNAP), which collects data on the processes and outcomes of stroke care up to 6 months post-stroke for more than 90% of acute stroke admissions to hospitals in England, Wales, and Northern Ireland. Every year data from approximately 85,000 patients are collected. SSNAP publishes quarterly and yearly analysis of results on its website [16].

#### Clinical audit

Foy et al. [17] recently revisited the case for national audits being effective and how they may be improved. Audit and feedback have been found to improve care, for example by showing individuals or providers that they are outliers, but it is important that recipients of the feedback are convinced by the audit, see it as specific to them and that audit promotes improvement action beyond simply measurement. A barrier to accepting feedback is the belief (true or otherwise) that “my patients are different”. Also, persistent negative feedback can lead to disconnection from the process of quality improvement. Foy calls for more intelligent use of audit with the call.

*“Audit and feedback are widely used, sometimes abused, and often under-realised in healthcare. More imaginative design and responses are overdue; these require evidence-informed conversations between clinicians, patients, and academic communities. It is time to fully leverage national audits to accelerate data guided improvement and reduce unwarranted variations in healthcare. The status quo is no longer ethical.”* Foy et al. 2020.

We respond to this challenge by using state-of-the-art modelling and machine learning tools that:

1. Are co-produced with clinicians to maximise perceived usefulness and minimise perceived threat.

2. Allow for differences in hospital patient populations (no ‘one target fits all’ approach).

3. Are patient-centred – focussing on outcomes as well as thrombolysis use. We will also identify types of patients where decision-making differs between hospitals, exemplified by artificial patient vignettes.

4. Are comprehendible by clinicians to build acceptance/validity.

5. Are action-focussed – identifying the actions to prioritise that will make most difference.

We are encouraged by discussions we have had on outputs from our previous work with several of the new Integrated Stroke Delivery Networks (ISDNs). Our existing work has stimulated significant interest already, particularly in the bespoke nature of the analysis and feedback. This encourages us regarding positive engagement with these improvement networks, especially regarding support with involving sites and/or clinicians that might otherwise be reluctant to engage or are sceptical about nationally-dictated ‘top down’ or ‘one size fits all’ targets.

## Summary of findings from SAMueL-1

We built clinical pathway simulation models, and clinical decision-making models, based on patient-level data from SSNAP. We built machine learning models that would closely replicate the clinical decisions made at each hospital, predicting if a patient who arrived within the treatment window would receive thrombolysis. The decision models are based on clinical pathway timings and patient clinical features recorded in SSNAP, such as age, components of the stroke severity scale (National Institutes of Health Stroke Scale; NIHSS), co-morbidities such as atrial fibrillation etc. The clinical decision-making models allow us to ask the counter-factual question, “What treatment would my patient be likely to receive at other hospitals?”. The clinical pathway simulation models predicted each hospital’s thrombolysis rate with an average absolute error of less than 0.5 percentage points. The clinical decision-making models predicted clinical decisions with 85% accuracy (achieving 84% sensitivity and specificity simultaneously) for those patients arriving within 4 hours of known stroke onset, with neural networks or random forest models having the highest accuracy.

Using our models, we found that about half of the current inter-hospital variation in thrombolysis is accounted for by differences in local patient populations. Most of the remaining inter-hospital differences were attributable to differences in clinical decision-making and, to a lesser extent, difference in hospital processes such as door-to-needle time.

We then tested three alternative scenarios at each hospital: 1) What if door-to-needle time was 30 minutes?, 2) What if all hospitals determined stroke onset time at least as frequently as the current upper quartile of hospitals?, 3) What if clinical decisions were made according to the majority vote of 30 top ‘benchmark’ hospitals? These benchmark hospitals are the 30 acutely-admitting stroke units with highest predicted users of thrombolysis using a standard set of 10,000 patients passed through all hospital decision models. The infographic below summarises our modelling findings. We found that making these changes at all hospitals would increase the national average thrombolysis rate to 18-19% (range 6-27%). The change that would have most impact would be alignment of clinical decision-making with hospitals more enthusiastic in their use of thrombolysis, then through better ascertainment of stroke onset times, and finally through speeding internal processes - although reducing door-to-needle time has a larger effect on overall clinical benefit, as they will benefit all patients who receive thrombolysis. For every additional 10 patients treated under these scenarios the primary reason was: clinical decision making in 5, determining stroke onset time in 4, and door-to-needle time in 1. The modelling produces a bespoke breakdown for each hospital, giving the realistic and achievable thrombolysis rate, and the impact of each component - helping to identify at each hospital which change would make the greatest difference to outcomes for their own local population. This is an important finding as prior to this, most improvement effort in thrombolysis has been based on the generalised assumption that the largest improvements in thrombolysis rate come from reductions in door-to-needle time [13].

{numref}`Figure {number} <samuel1-summary>` below shows a summary of findings from SAMueL-1.

:::{figure-md} samuel1-summary
<img src="./samuel1_summary.png" width="800px">

A summary of findings from SAMueL-1. 
:::

### Previous qualitative research

During SAMueL-1 we held physician workshops and conducted semi-structured interviews with groups and individuals. We found attitudes to our clinical pathway simulation and machine learning were related to whether the physician came from a hospital with either a higher or lower use of thrombolysis.

Doctors from hospitals with higher thrombolysis use:
Were interested in the modelling and what it might mean for their own local circumstances.

* Could see where it might help and identify how thrombolysis could be improved.

* Wanted to know more about how changes might affect adverse events and outcomes.

* Came from a hospital where there had been more effort/investment in the stroke pathway.

Doctors from hospitals with lower thrombolysis use:

* Were interested in the modelling and what it might mean for their own local circumstances, but were more cautious or sceptical.

* Wanted to provide best care, but worked in hospitals where there had been less work on, or investment in, the stroke pathway (e.g. fewer doctors, no specialist stroke nurses, poorer access to imaging).

* Tended to think their patients were different (e.g. they arrived later, had more complex needs, were not classic/typical stroke).

* Were concerned that increased use of thrombolysis would cause more harm than good.

## SAMueL-2 aims and objectives

The primary aims of the project are:

1.To maximise the impact of national comparative audit on clinical practice change in thrombolysis through the development and use of sophisticated hospital-level analysis and bespoke feedback. This analysis, allowing for differences in hospital patient populations, will investigate both the benefit and potential harms of thrombolysis. Hospitals will be compared with both national benchmarks and with a group of hospitals with similar patient populations.

2. To evaluate the potential health economic impact of realistic and achievable alterations to the acute stroke care pathway.

3. Using co-production with clinicians, determine the best way to use and present the outputs from SAMueL-2 to increase impact and reduce unwarranted variation in clinical practice in thrombolysis.

Based on clinician feedback received during SAMueL-1, and feedback received during first stage review, the specific objectives of this project are as follows:

### Machine learning and clinical pathway simulation

We will build significantly on the machine learning of SAMueL-1:

1. *Outcomes*: Include prediction of clinical outcomes at 24 hours after thrombolysis, discharge, and 6 months in machine learning, and prediction of thrombolysis-related haemorrhage. This objective is to address concerns that using higher-thrombolysing hospitals as the benchmark may drive thrombolysis use that may cause more harm than good.

2. *Organisation factors*: Include factors from SSNAP organisational audit into our machine learning model predicting thrombolysis use and outcome. This objective addresses questions of whether there are key organisational factors are associated with higher thrombolysis use.

3. *Ambulance response*: Include ambulance response times in clinical pathway simulation. This objective addresses the observation from SSNAP that in recent years improvements in door-to-needle time have been cancelled out by lengthening pre-hospital onset-to-arrival times [18].

4. *Thrombectomy*: Extend the application of this approach to thrombectomy (endovascular treatment of stroke). This extension will apply to both the clinical pathway simulation model and the machine learning models. This objective responds to the developing landscape of stroke treatment. Thrombectomy numbers in the UK are likely to remain too limited for robust analysis through machine learning, but we will pilot an extension that may include use of thrombectomy as well as thrombolysis.

### Incorporate Health Economic models

This project shares investigators with the NIHR Programme Grants for Applied Research PEARS (Promoting Effective And Rapid Stroke care) and OPTIMIST (OPTimising IMplementation of Ischaemic Stroke Thrombectomy). These projects have implemented, or are implementing, health economic modelling for use and speed of thrombolysis and thrombectomy. In this project we will incorporate and adapt health economic methods developed by these other NIHR projects and apply them in our modelling.

### Improve intelligibility and trust in modelling and machine learning

1. Implement Shapley values, a recently developed method that may be used in all machine learning model types, to explain the contribution of individual features to predictions the model is making. This responds to a lack of trust from some clinicians in the concept of predictive modelling. We will allow them to see how the model is making predictions and which factors influence the model prediction more towards or away from giving thrombolysis.

2. Improve methods for patient clustering, such as by using decision-tree distance in random forests, or embedding distance in neural networks. This will more easily identify groups of similar patients where clinical decision-making varies between hospitals, and identify typical patients in each group. Being able to measure similarity between patients (and hence patient populations) will also allow us to find hospitals with similar patient populations for use as peer comparators.

3. Generate dashboards and other methods for model interrogation to augment the key statistics. This seeks to make the models more transparent and understandable, and hence increase acceptance and gain traction. We will produce pilot dashboards in a streamlit.io framework (currently being adopted by SNAP) that may be adopted and/or refined by SSNAP and may inform initiatives in other national audits.

4. Investigate bias in the model. We will analyse two types of bias: 1) Bias that reflects real-world bias such as differences in hospital decision-making regarding whether patients with pre-stroke disability should receive thrombolysis, and 2) bias in the model whereby model accuracy is not equal for all subgroups.

### Create synthetic data and patient vignettes

Synthetic data allows people to explore a machine learning model in more detail with large cohorts of representative data, and is therefore beneficial to the open exploration of issues and uncertainties, and to open science (our synthetic datasets will be published so that allow other groups to apply novel methods and tools to address this pro). Patient vignettes may be used to provoke discussion between clinicians on when to use thrombolysis. We will extend our work in two areas:

1.  Generation of synthetic patient-level stroke data. This data will resemble raw SSNAP data.

2. Generation of synthetic patient vignettes which convert SSNAP-like data into a clinical vignette for discussion. We piloted this approach in the first project and found clinicians engaged with these well.

### Explore how best to incorporate modelling and machine learning into local improvement

We will carry out qualitative work to answer the question “Given existing variations in thrombolysis use, what is the best way for us to use and present the outputs of machine learning to reduce unnecessary variation and promote best patient outcomes?” This work will form a vital bridge between clinicians (users) and the modelling team to ensure that the science translates to real world settings and practice.

We will recruit up to 40 clinicians from hospitals across the spectrum of thrombolysis use (ensuring we get good representation from those hospitals with lower thrombolysis rates) to a clinician panel that will be asked to provide feedback and critical comments via regular meetings and email contact throughout the project. Specific planned activities include: 

1. Identify required improvement/refinements to the SAMueL-2 tool. We will hold co-production workshops with clinicians throughout the project to present the SAMueL-2 tool results and dashboards and gather feedback.

2. Gather feedback on synthetic patient vignettes. We will ask up to 20 of these clinicians to provide feedback on synthetic patient vignettes, and related material on differences in clinical decision-making, using think aloud interviews. This will help shape how this work is presented in order to maximize reflection on clinical decision-making around thrombolysis, which we have identified as the most significant modifiable source of inter-hospital variation in thrombolysis use.

3. Explore intelligibility and trust in modelling and machine learning. We will again use think aloud interviews with approximately 20 of these clinicians to explore intelligibility and trust in modelling and machine learning and to understand how the SAMuel-2 tool could address individual scepticism and organisational barriers to improving rates of thrombolysis.

In addition to these activities, we will work flexibly and responsively with this panel to explore specific implementation questions that emerge during the project, for example convening virtual meetings to examine how best to configure the dashboard, or to understand the kinds of health economics modelling they would find most useful. Qualitative data will comprise meeting notes, interview transcripts and workshop outputs which will primarily be analysed using a combination of thematic approaches and framework analysis.

### Promoting Open Science

We will continue to work using the principles of open science, as described by The Alan Turing Institute in The Turing Way.1 Using fully open code published in an online Jupyter Book like SAMueL-1, and using synthetic data, we hope this project will be useful as an example to others working with large publicly-funded datasets.

## Research plan and methods

### Overall attribution of requested funding

Leadership & management: £25,970; Modelling and health economics: £171,284; Qualitative (co-production): £134,726 (+ £8,640 NHS support costs); PPI: £5,665; Dissemination: £2,240; University overheads: £256,515.

### Clinical pathway simulation and machine learning

The key methodology of the project will be based on the methodologies employed in SAMueL-1, namely:

* *Clinical pathway simulation*: Based on Monte-Carlo simulation using Python/NumPy. Prediction of probability of good outcome derived from a meta-analysis of clinical trials and is based on age group and time from onset to treatment [5].

* *Machine learning*: predicting likelihood of receiving thrombolysis using patient and clinical features, time of stroke, time of arrival and scan, and hospital attended. Based on extensive testing in SAMueL-1, we will use random forests and neural networks. Use of these two contrasting machine learning methods will ensure the robustness of our results.

Clinical pathway simulation will be enhanced from SAMueL-1, in the following way:

* Incorporation of ambulance response, travel, and on-scene times (now available in SSNAP), allowing for ‘what if?’ testing of scenarios that alter pre-hospital timings.

Machine learning will be very significantly enhanced from SAMueL-1 in the following ways:

* Prediction of patient-level outcomes and risk of thrombolysis-related haemorrhage, based on data in SSNAP (24 hour NIHSS, modified Rankin Scale (mRS) at discharge, mRS at 6 months, label of thrombolysis-related haemorrhage). Note: mRS at 6 months is only partially complete, with just over 40% of those who survive to discharge having a recorded outcome at 6 months. We will test our ability to predict 6-month mRS (and therefore impute it when missing) using regression machine learning algorithms (e.g. random forests regression, neural network regression). A ‘fall-back’ strategy is to base outcome models just on 24 hour NIHSS, mRS at discharge, and thrombolysis-related haemorrhage.

* Incorporation of organisational factors (such as staffing) for each hospital. This will come from the biennial SSNAP organisational audit being conducted in October 2021.

### Building acceptance of, and trust in, modelling

An important focus in SAMueL-2 will be building methods to demonstrate trustworthiness of the models. We will be guided by the FAT-ML Principles for 
Accountable Algorithms (https://www.fatml.org/resources/principles-for-accountable-algorithms):

* *Responsibility*: Allow people to highlight issues with algorithms and have a mechanism to address them.

* *Explainability*: Ensure that algorithmic decisions can be explained in non-technical terms.

* *Accuracy*: Identify and communicate sources of error and uncertainty in the algorithms and the data used to train the algorithm.

* *Auditability*: Allow others to probe, understand, and review the behaviour of the algorithms.

* *Fairness*: Ensure that algorithmic decisions do not create discriminatory or unjust impacts when comparing across different demographics (e.g. race, sex, etc).

### Conceptual model for decision-making

We will explore clinical decision-making in two ways: 1) A machine learning model, and 2) Qualitative research. An overall conceptual model is shown in Figure {numref}`Figure {number} <conceptual>`.

:::{figure-md} samuel1-summary
<img src="./conceptual.png" width="800px">







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

We will explore clinical decision-making in two ways: 1) A machine learning model, and 2) Qualitative research. An overall conceptual model is shown in {numref}`Figure {number} <conceptual>`.

:::{figure-md} conceptual
<img src="./conceptual_model.png" width="800px">

Conceptual model of decision-making
:::

Machine learning models are necessary simplifications of real-world decision-making. This is especially true when applying these models to audit data as, though extensive data is available, we are limited to the data that has been collected and stored nationally. We do not expect the machine learning model to incorporate all aspects of clinical-decision making, but results from our previous project show that we can achieve an ROC-AUC of 92% and an overall accuracy of 86% for those patients arriving at hospital with time left to give thrombolysis. The model therefore encapsulates a lot of the information that drives decision-making (and the planned project will add some further information to the model inputs, so we may improve accuracy). These models reveal differences in decision-making such as attitudes to giving thrombolysis to milder strokes, to patients with pre-existing disability, or to patients with imprecise stroke onset times.

Including in our modelling are explanatory models showing what factors are most influential in the model, both overall and for individual patients. We know our models are ‘well calibrated’ – that is when the model has high certainty on whether a patient will receive thrombolysis or not, then it is almost always right. But when the model has low certainty then the accuracy of the model is worse. We will explore what the characteristics of the input that enable the model to be certain, and what are the input characteristics of the model when it is uncertain (we will also perform a similar analysis on looking at the characteristics of patients with predicted high variation in expected treatment between stroke teams).

Our qualitative research will add another layer to exploring decision-making, exploring the context of the decision-making – who is making the decision, and what the aspects of the decision-making that are not included in our machine learning model. This adds a ‘real world’ rich view on top of the machine-learning model, and through this work we will also explore how we might best influence decision-making.

### Clustering of patients and identification of hospitals with similar patient populations

Clustering of patients, using similarity metrics between patients, allows us to identify ‘typical’ patients that exemplify key differences in decision-making between hospitals. By generating similarity metrics between patients, we may also identify hospitals with similar patient populations. These may be used as comparator hospitals such as the ‘similar ten’ comparator groups used to compare Clinical Commissioning Group performance (https://www.england.nhs.uk/publication/similar-10-ccg-explorer-tool/), avoiding the problem of comparing hospitals with dissimilar populations. 

In SAMueL-1 we began this work, using both random forests (looking at distances between patient ‘leaves’ induced by the sequence of decisions used to classify them) and neural networks. An example of a novel approach to patient clustering, using neural networks, is shown below in {numref}`Figure {number} <cluster>`.

:::{figure-md} cluster
<img src="./cluster.png" width="400px">

Patient characteristic embedding, marking of those patients with a haemorrhagic stroke (red) as opposed to a non-haemorrhagic stroke (blue).
:::

We use *embedding layers* in a similar way to natural language models which encode words so that similar words (e.g. ‘big’ and ‘large’) end up close to each other in the encoded embedding space. The figure shows an example where the neural network encodes patients by similarity in decision-making, so that patients that appear similar when making decisions are located closely together. Using this approach, we find haemorrhagic patients closely clustered together (red cluster of patients in lower right of plot). Though not shown in this figure, we find other groups also closely located together elsewhere in the embedding space (e.g. patients who received thrombolysis, or patients who were not given thrombolysis but had very severe stroke). Expanding the number of embedding dimensions (here we use just 2 for simplicity) and using clustering techniques, such as k-means, should allow us to find types of patients that are typical of differences in decision-making between hospitals.

### Synthetic patient-level data and vignettes

#### Synthetic data

In SAMueL-1 we piloted generation of synthetic patient-level data that could be used to train machine learning models [21]. Techniques included SMOTE, generative adversarial networks, variational auto-encoders, and sampling from principal component analysis distributions. We found that synthetic data could be used to train and exemplify machine learning models with minimal loss in accuracy. We will extend and use these methods (e.g. with additional random-forest based methods and with an additional differential privacy layer) to generate large data sets of synthetic patient level data that can be used by people examining the model, or used to discuss examples of differences in decision-making between hospitals without risk of breaching patient confidentiality. We will assess the quality of the generated data by implementing methods to measure both utility (how well do the statistical properties of the synthetic data match those of the real data) and disclosure (how much information does the synthetic data reveal about the real data). Specifically, we will use:

* *Cross-classification* to measure the utility of the synthetic data. Cross-classification involves training a model on synthetic data and assessing its performance on real data. It is a method we have tested in SAMueL-1.

* *Random forest similarity* to measure the disclosure of the synthetic data. Disclosure can be minimised by ensuring that no point in the synthetic data is too close to any point in the real data. Using the similarity metric developed in our previous work, for each point in the real data we will find the closest point in the synthetic data. If the distance between these points is less than a threshold value, the synthetic data point will be perturbed to increase their distance.

* *A differential privacy* layer to add an extra layer of privacy2.

#### Vignettes

Below is an example artificial patient vignette from SAMueL-1.  This is based on key SSNAP data, with an imagined narrative that fits that data. Doctors have engaged well with these, which bring an additional human dimension to the raw data. In SAMueL-2 we plan to automate vignette generation by building up from a selection of appropriate blocks that match the SSNAP data.

*Sally is a 76 year old woman with hypertension who had a TIA three years ago, who was taking clopidogrel, bendroflumethiazide and a statin. She found her knee arthritis a bit of a nuisance when shopping. She started to feel a slight weakness in her left arm and leg as she was making dinner for herself and her husband, Roy, one Thursday evening. She thought her knee was playing up and put the 6 O’Clock news on the radio to take her mind off it. However, when Sally and Roy sat down to eat at 7pm he noticed that she was clumsy with her fork and he thought her face looked twisted on the right. As she had previously had a TIA, Roy was alarmed and quickly dialled 999. An ambulance arrived within 10 minutes, and by 7:28 pm she was being assessed in the emergency department of her local hospital.*

*The first doctor to see Sally quickly sent her for a CT brain scan, which happened at 7:59pm. Once back in the emergency department, the doctor assessing Sally noted her history of hypertension and TIA but that she was otherwise generally well. The doctor noted a minor drooping of her face, and a drift of her left arm and leg which were also slightly numb, and it seemed to make her left arm rather clumsy. Her NIHSS was 5. The scan showed no signs of haemorrhage, but there was an old lacunar infarct in the left hemisphere. The doctor decided that the risks of thrombolysis outweighed her potential to benefit as she thought the natural prognosis from her mild stroke was good even without thrombolysis. She subsequently admitted her to the stroke unit for observation.*

### Implementation

The code we generate will use all open Python libraries and, as with SAMueL-1, we will create a single Python file or Jupyter Notebook that will run all the standard analyses, off the back of a SQL query by SSNAP. We have worked with the SSNAP analytics team during SAMueL-1 on integration, and we will continue to work with them to ensure that our methodology and code is ready to implement following their upgrade to Microsoft Azure Database servers.

In order to enhance user-friendliness, SSNAP are currently reconfiguring their dashboards away from downloaded Excel sheets to interactive web pages using streamlit.io. We will similarly develop pilot output using streamlit.io that may be adopted or refined by SSNAP (streamlit.io is designed to be easily compatible with Jupyter Notebooks,  which is the environment our project already uses for clinical pathway simulation and machine learning).

### Health economic modelling

#### Overview

The health economic theme of SAMueL-2 is concerned with the short-term and long-term resource and health-related quality of life outcomes that are a consequence of differing levels and speeds of thrombolysis treatment. The analyses undertaken in SAMueL-2 will aim specifically at informing policy makers and commissioners of acute services about the health and resource consequences of differing levels of treatment.

#### Methodologies

The health economics methods will comply with appropriate guidelines, notably the Professional Society for Health Economics and Outcomes Research (ISPOR) Task Force on Good Research Practices-Modelling [22]. Models developed will take an NHS perspective within an extra-welfareist framework [23]. Specifically, the resources included within the analyses will be those consumed by the NHS in prehospital, hospital and community care settings. Health quality of life will be quantified using an instrument to which national tariffs apply and, when appropriate, ‘willingness-to-pay’ for gains in health-related quality of life will be applied. Health economic outcomes will be expressed in terms of the marginal difference between the service levels being modelled and the most appropriate alternative. The three types of economic analyses that will be used (Budget Impact Analysis, Cost-Effective Analysis and Cost-Utility Analysis) are listed in {numref}`Figure {number} <health_economics>`, together with their key summary inputs.

:::{figure-md} health_economics
<img src="./health_economics.png" width="600px">

Types of economic evaluation and their constituents.
:::

The economic analyses each report on a different facet of the consequences of different levels of service provision: 1) A Budget Impact Analysis is focused on the financial consequences (and is often reported in time-frames consistent with NHS budgetary cycles); 2) the cost-effectiveness analysis on efficiency of provision and, 3) the cost-utility analysis on the gains in health-related quality of life. Each analysis addresses different issues for policy makers. The estimation method used will be based on a Kaplan-Meier sample average type estimator. This method weights expected health-related quality of life and costs by the probability of survival.

The health economic analysis will use appropriate techniques to address the issue of uncertainty in estimates. Uncertainty is particularly relevant to economic models where data is drawn from different sources [24]. Appropriate sensitivity analyses will be carried out alongside estimation of overall uncertainty around the results of each analysis. Such sensitivity analysis may be informed, for an example, by comparison of the Northumbrian patient cohort with the national SSNAP data set obtained by the project for the machine learning and clinical pathway simulation modelling.





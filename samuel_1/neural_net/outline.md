# Outline - what is in this section?

This section describes experiments using neural network classifiers to predict whether a patient would, or would not, receive thrombolysis. Data is restricted to admissions within 4 hours of stroke onset (to units that have at least 300 patients, and 10 thrombolysis uses, over three years)

This section contains the following notebooks:

## Modular neural networks

Modular neural nets split data into three groups: 1) hospital id, 2) patient/clinical characteristics, 3) pathway times/timings. Each subgroup of data is processed by a neural subnet, the output of which may be a vector of any number of values - here we use 1 and 2 values per subnet output. The output from the subnets is combined in an additional layer in the neural network, and that layer outputs a sigmoid probability of receiving thrombolysis. This is called 'embedding' of the three subgroups of data.

When the subnets output a single value, this will condense each of the subgroups down to a single value that will be used in the final layer to determine probability of thrombolysis. This allows, for example, ranking of patients suitability for thrombolysis determined by a consensus view from all hospitals, and similarly allows ranking of hospitals to be ranked by propensity to give thrombolysis, independent of their own patient population. When 2 or more output values are used for each subnet this allows more complex interactions between patients and hospitals, and offers the potential to cluster similar hospitals or patients by location of their output vectors.

The notebooks are:

* *Modular TensorFlow model with 1D embedding - Train and save models*: Trains 5 models (on 5-fold cross validation train/test data sets) and saves for later use. Each subnet outputs a single value.

* *Modular TensorFlow model with 1D embedding - analyse*: Analyses the saved models for: 1) Various accuracy scores, 2) Receiver-Operator Characteristic Curve, 3) Sensitivity-Specificity Curve, and 4) model calibration.

* *Modular TensorFlow model with 2D embedding - Train and save models*: Trains 5 models (on 5-fold cross validation train/test data sets) and saves for later use. Each subnet outputs a pair of values.

* *Modular TensorFlow model with 2D embedding - analyse*: Analyses the saved models for: 1) Various accuracy scores, 2) Receiver-Operator Characteristic Curve, 3) Sensitivity-Specificity Curve, and 4) model calibration.

* *Modular TensorFlow model with 2D embedding - Train and save model for 10k patient subset*: Train a model on all data exluding a 10k test set (the train and test set are balanced for thrombolysis use across each hospital).

* *Investigating the output of neural net embedding subnets*:  Investigate the output of the hospital and clinical subnets of the embedding neural network. 1) Examine the link between hospital subnet output and use of thrombolysis in hospitals - both the actual thrombolysis use, and the predicted thrombolysis use of a 10k set of patients passed through all hopsital moodels. 2) Examine the link between the patient clinical feature subnet output and the use of thrombolysis, and the link between patient features and the clinical feature subnet output.

* *Train an embedding neural network to discern 'contentious patients' from those with high agreement to thrombolyse*: In this notebook we use a pre-trained model (embedding neural network with 1D embedding, use to test a 10k cohort of patients) to predict thrombolysis use of all patients at all hospitals. Patients are then split into three groups: 1) *Agree not to thrombolyse*: Fewer than 25% of hospitals would give thrombolysis, 2) *Contentious*: 25% to 75% of hospitals would give thrombolysis, 3) *Agree to thrombolyse*: More than 75% of hospitals would give thrombolysis. We then train an embedding neural network model (using patient and pathway data subsets) to distinguishing between *Contentious* and *Agree to thrombolyse*. This is saved for more detailed analysis in a subsequent notebook.








# Confound Prediction

## Confound_prediction is a Python module to control confound effect in the prediction or classification model.

Any successful prediction model may be driven by a confounding effect that is correlated with the effect of interest. It is important to control that detected associations are not driven by unwanted effects. It is common issue in in neuroscience, epidemiology, economy, agriculture, etc. 

We introduce a non-parametric approach, named **“confound-isolating cross-validation”**, to control for a confounding effect in a predictive model. It is based on crafting a test set on which the effect of interest is independent from the confounding effect. 


### What expect from Confound_prediction?

Developed framework is based on anti mutual information sampling, a novel sampling approach to create a test set in which the effect of interest is independent from the confounding effect. The grafical illustration of classic and confound-isolating cross-validation:

<p align="center">
  <img src="https://github.com/darya-chyzhyk/confound_isolating_cv/blob/master/docs/Cross_validation_classic.svg" height="300"> <img src="https://github.com/darya-chyzhyk/confound_isolating_cv/blob/master/docs/Cross_validation_confound_isolation.svg" height="300"> 
</p>


### How does it work?

<p align="center">
  <img src="https://github.com/darya-chyzhyk/confound_isolating_cv/blob/master/docs/Confound_isolation_cv_evolution.svg" height="150">
</p>

**You provide us**

Variables:
&nbsp;
* *X* - data with shape (n_samples, n_features)
* *y* - target vector with shape (n_samples)
* *z* - confound vector with shape (n_samples)

Optional parameters
* *min_sample_size* - minimum sample size to be reached, default is 10% of the data
* *n_remove* - number of the samples to be removed on each iteration of sampling, default is 4
* *prng* - control the pseudo random number generator, default is None
* *cv_folds* - number of folders in the cross validation, default is 10

**We return you**

Variables:
* *x_test, x_train, y_test, y_train, ids_test, ids_train* - train and test of *X*, *y* and *sampled indexes*


## Installing
TBD

## Examples

### Example: create train set and test set without confounding effect

'''
python example/
'''

### Example: compare prediction on data sampled with different deconfounding methods

'''
python example/
'''

### Example: compare prediction on the data with different confound effect

'''
python example/
'''

### Example: evolution of mutual informatio and correlation on each itteration of *confound-isolation cross-validation' method

'''
python example/
'''

## Another methods
We also provide 2 state of the art in neuroscience deconfounding techniques:

&nbsp; 1. Out-of-sample deconfounding

&nbsp; 2. Deconfounding test and train jointly


## References

[1] TBD

[2] D. Chyzhyk, G. Varoquaux, B. Thirion and M. Milham, "Controlling a confound in predictive models with a test set minimizing its effect," 2018 International Workshop on Pattern Recognition in Neuroimaging (PRNI), Singapore, 2018, pp. 1-4.
doi: 10.1109/PRNI.2018.8423961 [PDF](https://hal.archives-ouvertes.fr/hal-01831701/document)


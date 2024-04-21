---
tags:
  - ml
---
-----------

## Contents:
- Random forest introduction
- Explanation of the method in initutive format 
- sampling methods used
- Evaluation metrics
- Different hyperparameters meanings 
- Bagging and boostrapping
- OOB evaluation
- Adv and disadv
- Implement in python and R


---------------

# Random forest regressor

- bagging method -> random forest -> low bias, low variance  
- consists of multiple decision trees which are created with randomly drawn samples from data (ie rows of data and also the features used)  
- row sampling and feature sampling -> decision tree.  it can also be row sampling with replacement ie the row values sampled by decision trees can be repeated to different decision tree  
- the final model result are combined as average of all the results from these ensemble of decision tree models and by majority voting in case of classification problem  
- Bootstrapping is the process of randomly sampling subsets of a dataset over a given number of iterations and a given number of variables.  
- Out of bag (OOB) evaluation -> training samples which are not selected by any decision tree are OOB data which can act as a validation set.
# Accuracy: 
`Accuracy is the proportion of true results among the total number of cases examined.`
### When to use: 
`valid choice of evaluation for classification problems which are well balanced and not skewed or No class imbalance.`
### caveats: 
`What if we are predicting if an asteroid will hit the earth? Just say No all the time. And you will be 99% accurate. My model can be reasonably accurate, but not at all valuable. so sparse target shouldnt use accuracy `

# Precision:
`what proportion of predicted Positives is truly Positive`
### when to use: 
`when we want to be very sure of our prediction`
### caveats: 
`Being very precise means our model will leave many (almost true)targets untouched`

# Recall:
`what proportion of actual Positives is correctly classified`
### when to use: 
`when we want to capture as many positives as possible.`
### caveats: 
`cannot use this metric standalone because if you predict 1 for all samples, recall will be 1. Thus metric is good but model is very bad`

# f1 score:
`F1 score is a number between 0 and 1 and is the harmonic mean of precision and recall.`
### when to use: 
`We want to have a model with both good precision and recall. So basically all the time`
### caveats: 
`The main problem with the F1 score is that it gives equal weight to precision and recall. We might sometimes need to include domain knowledge in our evaluation where we want to have more recall or more precision.`
`so to solve the caveat, weighted metric can be used if knowledge is present about which to give weight`
`Good metric for imbalanced dataset`

# Log Loss/Binary Crossentropy:
`Log loss is a pretty good evaluation metric for binary classifiers and it is sometimes the optimization objective as well in case of Logistic regression and Neural Networks. log loss decreases as we are fairly certain in our prediction of 1 and the true label is 1.`
### when to use: 
`When the output of a classifier is prediction probabilities. Log Loss takes into account the uncertainty of your prediction based on how much it varies from the actual label. This gives us a more nuanced view of the performance of our model.`
`caveats: It is susceptible in case of imbalanced datasets`

# Categorical Crossentropy:
`The log loss also generalizes to the multiclass problem. The classifier in a multiclass setting must assign a probability to each class for all examples.`
### when to use: 
`When the output of a classifier is multiclass prediction probabilities`

### caveats: 
`It is susceptible in case of imbalanced datasets.`

# AUC (Area Under the ROC Curve):
`ROC curve shows the trade-off between sensitivity (or TPR) and specificity (1 - FPR). Classifiers that give curves closer to the top-left corner indicate a better performance. As a baseline, a random classifier is expected to give points lying along the diagonal (FPR = TPR).`
### AUC ROC indicates:
`how well the probabilities from the positive classes are separated from the negative classes. It measures the quality of the model's predictions irrespective of what classification threshold is chosen, unlike F1 score or accuracy which depend on the choice of threshold.`

### Caveats: 
`Sometimes we will need well-calibrated probability outputs from our models and AUC doesn't help with that.`

### Handling imbalanced Data

#### 1 SMOTE(SyntheticMinorityOversamplingTechnique) — upsampling:-
`It works based on the KNearestNeighbours algorithm, synthetically generating data points that fall in the proximity of the already existing outnumbered group. The input records should not contain any null values when applying this approach.`

#### 2 DataDuplication — upsampling:- 
`In this approach, the existing data points corresponding to the outvoted labels are randomly selected and duplicated.`

#### 3 Downsampling 
`Is a mechanism that reduces the count of training samples falling under the majority class. As it helps to even up the counts of target categories. By removing the collected data, we tend to lose so much valuable information`

#### 4 Tomek(T-Links):-
`T-Link is basically a pair of data points from different classes(nearest-neighbors). The objective is to drop the sample that corresponds to the majority and thereby minimalizing the count of the dominating label. This also increases the borderspace between the two labels and thus improving the performance accuracy.`

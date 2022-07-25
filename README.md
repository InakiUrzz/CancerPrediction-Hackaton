# CancerPrediction-Hackaton
___

### Objetive:

- Understand the dataset and clean it if applicable.

- Build classification models to predict whether the cancer type is malignant or benign, "diagnostic" variable 0 benign and 1 malignant.

- Fit hyperparameters and compare evaluate metrics


## Some general information:
___
Challenge made for the Nuwe and IT Academy Hackathon, Barcelona, where a predictive model was made to identify the type of tumor.
An exploratory analysis of the data was made and a Catboost Classifier classification model was applied within a Pipeline to predict the type of tumor according to the data given.
___

## Some facts about Breast Cancer:
- Breast cancer is one of the most studied types of cancers.
- Women over 40 years old are at the highest risk of breast cancer.
- According to a study by the University of California, San Francisco, it was concluded that women who have dense breast tissue have a higher risk of developing this type of cancer.
- It is mistakenly believed that this type of cancer only affects women, but it has been proven that men can also develop it, although in a lower percentage.
- It is important to know the difference between a benign tumor and a malignant one. The former are soft, move and can be painful, while malignant tumors are hard, fixed and painless. From the age of 40 it is recommended that mammography, mammography and other additional studies such as breast ultrasound, be performed annually, and even a few years earlier in high-risk women.
- The causes may be due to a high-fat diet, pregnancies at an advanced age or not having pregnancies, addictions such as alcohol and tobacco, starting monthly periods before the age of 12 or having menopause after the age of 55, hormone replacement therapies for a long time, no or little breastfeeding and a sedentary lifestyle are risk factors for developing breast cancer.
___

## Some conciderations to understand the dataset:

The way the dataset is structured was created by Dr. William H. Wolberg, a physician at the University of Wisconsin Hospital in Madison, Wisconsin, USA. To create the dataset, Dr. Wolberg used fluid samples, taken from patients with solid breast masses, and an easy-to-use graphical computer program called Xcyt, capable of performing analysis of cytologic features from a digital scan. The program uses a curve fitting algorithm, to calculate ten features for each of the cells in the sample, which calculates the mean value, extreme value and standard error of each feature for the image, returning a vector of 30 real values-

Attribute information:

- diagnosis: 0 tumor is benign, 1 tumor is malignant.

- radius (mean of the distances from the center to the perimeter points)
- texture (standard deviation of the grayscale values)
- perimeter
- area
- smoothness (local variation of the lengths of the radius)
- compactness (perimeter² / area - 1.0)
- concavity (severity of concave portions of the contour)
- concave points (number of concave portions of the contour)
- symmetry
- fractal dimension ("approximation of the coastline" - 1)

For each image, the mean, standard error and "worst" or largest (mean of the three largest values) of these features were calculated, resulting in 30 features.
___

## Conlusion: 

- Different types of algorithms were tested such as, Random Forest Classifier,AdaBoostClassifier, KNeighbors Classifier, Logistic Regression, etc.

- The best F1 macro was obtained without stratifying the sample, with CatBoosClassifier 0.985 but it was a bit far from our Cross Validation having a bit of overfitting, to which, being a subject as sensitive as cancer, I decided to use the stratified sample and keep the f1 0.976 macro which is closer to our CrossValidation. This one was obtained with the CatBoost Classifier again, with a result of 0.976 wich was a bit overfitted but it´s a very good result.

- By having strongly correlated variables, it was possible to obtain good results, which also indicates that the quality of the data was also good.

- Although this usually gives good predictions when classifying a tumor as benign or malignant, this should not be considered as absolute truth, but a tool on which to rely so that they can reach an accurate conclusion. This does not speak of certainties but of the probability that there is (according to the data previously obtained and analyzed) that a tumor is benign or malignant.

- There is a strong correlation between tumor texture damage and tumor size area. The larger the area of the tumor, the smaller the lesion texture

- There is a positive trend between the average number of concave points and the average radius in both benign and malignant tumors. Benign tumors are located in an area where the values of both features are lower while malignant tumors have higher values.
___

## Proposed Solution:
- A web page should be created so that the Machine Learning Model can be deployed, and anyone who has their mammography results, but above all doctors, can interact and upload the data to obtain a prediction of the type of tumor that is being analyzed.

- New technologies such as Machine Learning and artificial intelligence can serve as a diagnostic tool.
___

### Libraries used:

- Python version 3.9.13
- Pandas
- Numpy
- Scikit Learn
- CatBoost
___

### Documentation:

- Cancer Breast Data : https://www.ngenespanol.com/ciencia/informacion-sobre-el-cancer-de-mama/
- DataSet = Dataset given by Nuwe CancerPrediction-Hackaton: https://nuwe.io/challenge/repte-4-models-de-classificacio
- Cancer Breast DataSet explanation : http://archive.ics.uci.edu/ml/datasets/breast+cancer+wisconsin+%28diagnostic%29
- CatBoost Classifier: https://catboost.ai/en/docs/concepts/python-reference_catboostclassifier
- SKLearn Pipeline: https://scikit-learn.org/stable/modules/generated/sklearn.pipeline.Pipeline.html
- Cross Validation: https://scikit-learn.org/stable/modules/cross_validation.html

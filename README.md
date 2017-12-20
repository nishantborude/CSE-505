# CSE-505

This project is the machine learning implementation in python of the paper 'Probabilistic Logic Models and their application to Breast Cancer'.

The paper mainly focuses on the data analysis of the Breast Cancer dataset and applying ILP models to probabilistic data to generate new first order sentences. The analysis comprises of statistical analysis of the predictions done by experts in the field vs the predictions done by ILP models on the same dataset.

The original project consists of multimodal features of the particular disease collected with collaboration of specialists in the field and the ILP scientists hence the data is confidential.
My implementation of the project progresses in the exact same way as the paper depicts but in python on a different dataset.

## Files

1. project\_ilp\_dementia-id3\_final: Contains python implementation of ID3 Decision Trees for Dementia data analysis.
2. project\_ilp\_dementia-svm: Contains python implementation of Support Vector Machines for Dementia data analysis.
3. project\_ilp\_schiz\_id3-feat\_sel: Contains python implementation of ID3 Decision Trees for Schizophrenia data analysis.
4. final\_oasis\_dementia.csv: Dataset Dementia
5. train\_FNC.csv, train\_SBM.csv, train\_labels.csv: Dataset Schizophrenia

## Dataset

I used two different datasets to get different results.

1. Dementia dataset: The data is obtained from the Oasis webpage and consists of 12 different features originally. I reduced the number of features to 9 selecting only those which have maximum impact on the training and testing. These features are first needed to be normalized for best parameter tuning. 

2. Schizophrenia Dataset: Kaggle MLSP 2014 provides this dataset. It consists of 410 multimodal features divided into two sets. These features are combined together for training.

### Data Credits: 
Oasis: http://www.oasis-brains.org/
Kaggle: https://www.kaggle.com/c/mlsp-2014-mri

## Approach

1. Data Preprocessing: The implementation for both datasets is almost similar for the data preprocessing part. I wrote the preprocessing function for the Dementia data in order to normalize the different columns. I took the maximum value of each column and divided the entire column with that value in order to bring the feature set in the same ranges. The other dataset consists features in the comparable range hence, doesn't need to ne normalized.

2. Data split: The data needs to be divided into train and test sets for getting the accuracy for predictions. Normally it is split as 60%-40% but as the data for Schizophrenia is limited (86 entries only), I split them into 70-30 ration to get a better training accuracy. The other data is divided into 80-20 ratio(336 rows total).

3. Model Building: Individual models are trained for the respective datasets with default parameters and their predictions are tested on the test data. 

4. ROC curve: The paper shows a plot of the actual prediction accuracy vs test accuracy, known as the Receiver Operating Characteristic Curve which shows the accuracy of the trained model on making predictions. The method to do that is to calculate all metrics such as true positives, true negatives, false positives and false negatives from the predicted and output dataset. Then calculate the true positive and false positive rate from the formula to plot the ROC.

## Results

1. Dementia: AUC accuracy averaging to 98.5
2. Schizophrenia: AUC accuracy averaging to 60.2

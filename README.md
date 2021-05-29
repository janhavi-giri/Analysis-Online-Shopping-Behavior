# Kaggle_Projects_Part_2

Kaggle data science project conducting complete analysis of online shopping behavior.

This project is based on "Online Shoppers Purchasing Intention Dataset Data Set" https://archive.ics.uci.edu/ml/datasets/Online+Shoppers+Purchasing+Intention+Dataset

Goal: Develop Machine Learning Models to present a complete analysis for online shopping behavior data set.

Task 1: To build a predictive classification model (ensuring optimal features and classifier) on data entries corresponding to the months of June-Dec, and test the model on data entries corresponding to Feb-March. 

Methods:

	1. EDA

	2. Data pre-processing: selecting input/target features, label encoding
  
	3. Feature selection: pearson correlation and feature importance from decision trees
		
	4. Feature scaling such that all features lie b/w 0 and 1

	5. Classifiers: Linear: Logistic Regression/Non-linear: Kerne SVM(Poly/RBF)
  
	6. Hyper parameter tuning

	7. Auto-ML for comparison and verification
  
	8. Output Metrics: Accuracy, Precision, Recall, F1-Score, Classification report, Confusion matrix, and ROC_AUC curve.
  
Results: 

   Linear and Non-linear Classifiers
   
  	 LR_not_tuned	LR_tuned	KSVM_POLY	KSVM_RBF
          
	accuracy	0.854137	0.947872	0.898135	0.932568

	precision	0.384454	0.653571	0.476684	0.588235

	recall	 0.938462	 0.938462	0.943590	0.923077

	f1 score	0.545455	0.770526	0.633391	0.718563

	roc_auc	 0.957698	0.944436	0.963843	0.973034

Verification with AutoML:

AutoML resulted in Gradient Boosting Classifier as the best classifier to perform the classification task.

	Kernel SVM (rbf) vs GradientBoostingClassifier
		KSVM_RBF	XGB_CLASS
	accuracy	0.932568	0.933525
	precision	0.588235	0.811111
	recall	0.923077	0.374359
	f1 score	0.718563	0.512281
	roc_auc	0.973034	0.959034
	
The accuracy of the GradientBoosting Classifer and Kernel SVM (rbf) are similar. However, the precision for the former is: 81.1% which is higher than the latter with 58.8%. 
Moreover, the roc_auc for Kernel SVM (rbf) is  higher than the "GradientBoostingClassifier" which implies that the Kernel SVM (rbf) model does a good job in separating the classes.Though, recall is lower for the "GradientBoostingClassifier".

Conclusion:

Best performance with regards to separating the postive and negative classes, among the chosen linear/non-linear classifier is the RBF Kernel SVM classifier with roc_auc of 0.97.


Task 2: To generate user-bahavior clusters based on the purchasing behavior data for the complete dataset. 

Methods:

Clustering using K-means; Identifying clusters of customers that are highly likely to purchase vs non-purchasers and determining potential customers to increase purchase.
#Clusters found from: ProductRelatedDuration, BounceRates, PageValues, VisitorType, and Revenue

Output metrics: Silhouette score 

Results:

Clusters being categorized into categories: Non-Purchasers, Targets (potential customers), and Purchasers based on the 'ProductRelated_Duration' i.e. Purchasers are the ones with largest 'ProductRelated_Duration' and vice-versa for 'Non-Purchasers'. Targets are the intermediate ones who do not end-up purchasing.Categorized them into 3 instead of 5; which is equivalent to having 3 clusters instead of 5. This seems to be better solution as seen from the analysis shown.

Conclusion:

Based on clustering and further analysis, we see that the returning visitors dominate as customers. How can we encourage new_visitors customers so that they become purchasers?




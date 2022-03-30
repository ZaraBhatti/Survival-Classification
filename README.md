#### Using Machine Learning to evaluate the use of geriatric assessment scores in predicting survival for elderly leukemia patients after Allogenic Hematopoietic Cell Transplantation

The uncertainty of post-transplant survival is a great obstacle when it comes to the treatment of older blood cancer patients therefore discovering more prognostic factors that can be applied to post-transplant outcome prediction would hugely benefit this area of cancer research.

This is the view that motivates this study in which the aim is to answer the following question: <b>‘Does using a set of geriatric assessment scores as a predictor for post-allogenic HCT survival in elderly leukaemia patients perform as well as existing prognostic factors?’</b>. The exact set of predictors to be compared were selected after Exploratory Data Analysis (please see the FEATURE SELECTION section below).

*The complete code is contained within a single Jupyter Notebooks. Within the notebook there are comments alongside the code for guidance.*

<details><summary>DATASET</summary>
<p>
  
The dataset used within this study has been taken from the website of the Center For International Blood & Marrow Transplant Research and is openly available for public use [link](https://www.cibmtr.org/ReferenceCenter/PubList/PubDsDownload/Pages/default.aspx). 

It was retrieved from a publication by Olin et al. (available [here](https://doi.org/10.1182/bloodadvances.2020001719)) and contains data on patients who have undergone a transplant with their survival times. The dataset contains 26 features, 329 samples and is balanced.

</p>
</details>

<details><summary>FEATURE SELECTION</summary>
<p>
  
Through visualisation and survival analysis, a final set of clinical features and geriatric assessment features were selected (see below for definitions). Thus, the initial question can now become more specific: <b>‘Does using BOMC, IADL, MOS and TUG (geriatric assessment scores) as predictors for post-allogenic HCT survival in elderly leukaemia patients perform as well as Karnofsky score, age group, HCT-CI and graft source (existing prognostic factors)?’</b>.
  
![alt text](https://github.com/ZaraBhatti/group/blob/main/features_table.jpg?raw=true)

</p>
</details>

<details><summary>PLAN</summary>
<p>
  
Since the dataset is balanced and data follows non-normal distribution, the following models were chosen for this study: KNN classifier, Decision Tree Classifier, SVM, Random Forest, XGBoost and an MLP Classifier. The models will take either the clinical features OR the geriatric features as input and predict death (0) or survival (1).
  
Matthews Correlation Coefficient (MCC), Confusion Matrix, F1-score, ROC-AUC, and Accuracy were selected as potential performance metrics for this classification task. 
Using these metrics, the best model using clinical features as input will be selected and the best model using geriatric features as input will be selected.
  
The Mann-Whitney U Test will then be used to statistically compare the clinical model and the geriatric model to see if there is a statistically significant difference in their performances (i.e. one can be said to perform better than the other).

</p>
</details>

<details><summary>RESULTS</summary>
<p>
  
The KNN classifier model performed the best with both types of input therefore the performances of these two models were compared. The generated p-value was >0.05 therefore the null hypothesis is accepted and it can be concluded that there was no significant difference in the models' performances when using clinical features compared to geriatric assessment scores as the input features. 
  
Both sets of features had similar performance and prognostic capabilities therefore the answer to our question <b>‘Does using BOMC, IADL, MOS and TUG (geriatric assessment scores) as predictors for post-allogenic HCT survival in elderly leukaemia patients perform as well as Karnofsky score, age group, HCT-CI and graft source (existing prognostic factors)?’</b> is YES, according to the results of this study.
  
The addition of these features within clinic may provide clinicians with more factors to help confidently predict their patients’ survival and help to inform treatment decisions. This can have a great effect on the overall survival of elderly leukaemia patients as more patients may be recommended HCTs.
  
However, there are limitations to this study. The overall accuracy of the two best models were still low. This may be the case as patients can have vastly differing responses to treatment and diseases, although it would be quite interesting to apply deeper learning models to this dataset. Unfortunately, the size of the dataset used within this study was very small at 302 patients which may also play a part in the low reported accuracies. In the future, the study should be repeated with a larger dataset to see if the accuracy of the models increases as a result.

</p>
</details>

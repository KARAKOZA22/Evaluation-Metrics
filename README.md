# Evaluation metrics
<h2>Accuracy</h2>Calculating how many predicted instances are true over all the classes.
<h2>confusion matrix</h2> 
Contains <b>TP and TN </b> which are the truely predicted values, <b>FN, and FP </b> which are the false predicted values like in <b>False Negative (FN)</b> , it is classified as Negative but this is false, it is positive.<br><br>

![confusionMatrxiUpdated](https://github.com/KARAKOZA22/Evaluation-Metrics/assets/96451039/2d124035-b33f-473d-a511-109b38be6fd2)

<h2>Precision</h2>
It indicates how many values are truely predicted as positive from all predicted as positive
<h2>Recall</h2>
It indicates how many values are truely predicted as positive from all true labels as positive
<h2>F1-Score</h2>
It is the geometric mean between <b>Precision, and Recall</b><br><br>
<b>Geometric mean of [1, 2, 3, 4] = (1 * 2 * 3 * 4) ^ (1 / 4) = 2.2134</b><br><br>
<b>Arithmetic mean of [1, 2, 3, 4] = ( 1 + 2 + 3 + 4) / 4 = 2.5 </b><br><br>

![f1 score](https://github.com/KARAKOZA22/Evaluation-Metrics/assets/96451039/8555394f-a121-4d0b-86a5-07c1d9d7e3b0)


<h2>ROC Curve</h2>
<b> ROC = TP / FP </b><br><br>

![roc-curve-original](https://github.com/KARAKOZA22/Evaluation-Metrics/assets/96451039/57ce3080-effd-46b0-a019-023a456f0f52)

```
import matplotlib.pyplot as plt
from sklearn.datasets import make_classification
from sklearn.metrics import RocCurveDisplay
from sklearn.model_selection import train_test_split
from sklearn.svm import SVC
X, y = make_classification(random_state=0)
X_train, X_test, y_train, y_test = train_test_split(
clf = SVC(random_state=0).fit(X_train, y_train)
y_pred = clf.decision_function(X_test)
RocCurveDisplay.from_predictions(
plt.show()
```

<h2>Summary</h2>
Instead of Importing all the previous metrics, you can use classification report that displays all of them<br>

```
from sklearn.metrics import classification_report
y_true = [0, 1, 2, 2, 2]
y_pred = [0, 0, 2, 2, 1]
target_names = ['class 0', 'class 1', 'class 2']
print(classification_report(y_true, y_pred, target_names=target_names))

              precision    recall  f1-score   support

     class 0       0.50      1.00      0.67         1
     class 1       0.00      0.00      0.00         1
     class 2       1.00      0.67      0.80         3

    accuracy                           0.60         5
   macro avg       0.50      0.56      0.49         5
weighted avg       0.70      0.60      0.61         5
```



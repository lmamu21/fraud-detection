# Fraud-Detection

model_experiment_LogisticRegression.ipynb — ლოგისტიკური რეგრესიის მოდელის ტესტირება

model_experiment_DecisionTree.ipynb — გადაწყვეტილების ხის მოდელის ტესტირება

model_experiment_RandomForest.ipynb — შემთხვევითი ტყის მოდელის ტესტირება

model_experiment_XGBoost.ipynb — XGBoost მოდელის ტესტირება

model_inference.ipynb — საბოლოო მოდელის გამოყენება პროგნოზირებისთვის

## Feature Engineering
CustomPreprocessor კლასი:

* კატეგორიული ცვლადების რიცხვითში გადაყვანა
გამოვიყენე One-Hot Encoding და WOE Encoding ტექნიკები კატეგორიული ცვლადების რიცხვითში გადასაყვანად.

* Nan მნიშვნელობების დამუშავება
Nan მნიშვნელობების შესამცირებლად გამოვიყენე სხვადასხვა იმპუტაციის მეთოდები, როგორიცაა საშუალო, მედიანა და ყველაზე ხშირი მნიშვნელობებით ჩანაცვლება, რაც დამოკიდებული იყო ცვლადის ტიპზე და განაწილებაზე, ასევე ვცადე პროცენტულობის სხვადასხვა ზღვარი null მნიშვნელობებისთვის სვეტების წასაშლელად.


## Feature Selection
* გამოვიყენე RFE რათა შეგვემცირებინა ცვლადების რაოდენობა. ასევე, გამოვიყენე correlation filter მეთოდი, რათა გამეფილტრა ღირებულების არმქონე სვეტები.

## Training
### ტესტირებული მოდელები
Logistic Regression

Decision Tree

Random Forest

XGBoost

## საბოლოო მოდელი
საბოლოოდ, Random Forest მოდელს, რომელსაც ჰქონდა undersampled მონაცემები 0.3-იანი განაწილებით, ჰქონდა ყველაზე მაღალი roc_auc. 

## MLflow Tracking
სამწუხაროდ, ყურადღება არ მიმიქცევია რომ, run-ები უნდა შეესაბამებოდეს პრეპროცესინგის ნაწილებს. 
ჩემს ექპერიმენტებში სხვადასხვა არქიტექტურები დაყოფილია ექპერიმენტებად, მაგრამ run-ები შეესაბამება ამ არქიტექტურის ერთ კონკრეტულ მოდელს
სხვადასხვა პრეპროცესინგის პარამეტრებით (წესით ასევე უნდა გამეტესტა მოდელის სხვადასხვა ჰიპერპარამეტრებიც)
https://dagshub.com/lmamu21/fraud-detection.mlflow/#/experiments/1?searchFilter=&orderByKey=attributes.start_time&orderByAsc=false&startTime=ALL&lifecycleFilter=Active&modelVersionFilter=All+Runs&datasetsFilter=W10%3D 


## ჩაწერილი მეტრიკების აღწერა
MLflow-ში ჩავწერეთ შემდეგი მეტრიკები:

Accuracy

Precision

Recall

F1 Score

ROC AUC Score

## საუკეთესო მოდელის შედეგები
საუკეთესო შედეგები მიღწეულია Random Forest მოდელით, რომლის ROC AUC Score იყო 0.92. სატესტო მონაცემებზე kaggle-მა შეაფასა: 
Score: 0.872400 Private score: 0.845351

HR-Analytics: Predict whether employe get promoted or not
-------------------------------------------------------------

Dataset details : 
---------------------------------

  employee_id        -     Unique ID for employee
    
  department         -     Department of employee
    
  region             -     Region of employment (unordered)
    
  education           -    Education Level
    
  gender              -    Gender of Employee
    
  recruitment_channel  -   Channel of recruitment for employee
    
  no_of_trainings       -  no of other trainings completed in previous year on soft skills, technical skills etc.
    
  age                    - Age of Employee
    
  previous_year_rating   - Employee Rating for the previous year
    
  length_of_service      - Length of service in years
    
  KPIs_met >80%          - if Percent of KPIs(Key performance Indicators) >80% then 1 else 0
    
  awards_won?            - if awards won during previous year then 1 else 0
    
  avg_training_score    -  Average score in current training evaluations
    
  is_promoted            - (Target) Recommended for promotion


Model Used:
---------------

   The dataset shows that this is clearly a classification task and can be solved by a myriad of classification algorithms,
   I chose Support Vector Classifier(SVC) because of the flexibility it shows during training.
    
   Hyper Parameters chosen for:
        SVC: {kernel='linear', degree=3, probability=True}
        Random Forest: {'criterion': 'entropy', 'max_depth': 9, 'max_features': 'sqrt', 'n_estimators': 425}
   Provided the dataset was slightly unbalanced, the SVM model gave a better Recall score for the negative classes as compared to Random Forest.
   Hence, I chose SVM as the model to use for the API.

API:
----------

   I have made an API for the SVC model so that users can interact and use the model with ease.
   To make the API work I have used the Flask library which are mostly used for such tasks.
   I have also connected a HTML form to the flask app to take in user input and a CSS file to decorate it.

Deployment:
---------------

  The Flask API was deployed on the Heroku cloud platform so that anyone with the link to the app can access it online.
  I have connected this GitHub repository to Heroku so that it can be run on the Heroku dyno.
  I have used the Gunicorn package which lets Python applications run on any web server. The Procfile and requirements.txt should be defined with all the     details required before the deployment.



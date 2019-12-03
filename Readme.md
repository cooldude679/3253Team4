## 1.Introduction
ML Project - No Shows
The failure of patients to attend medical appointments (no-shows) costs healthcare systems a great deal of time and money. The aim of this project was to construct a machine learning model capable of predicting no-shows ahead of time. The data that was used provides the details of over 110,000 medical appointments scheduled over the course of April, May and June 2016 at various clinics in the Brazilian city of Vitoria.

Source: https://www.kaggle.com/joniarroba/noshowappointments


## Group Member
Arthur Sowinski;
Ibrahim Abu Nameh;
Michel Tayzon;
Vishal Valentine ;


## 2. Data Preparation 
Data is loaded from Kaggle.
https://www.kaggle.com/joniarroba/noshowappointments


This is a typical classification problem.  

## 3. Feaure Engineering

3. Feature Engineering

Creating new time-related features;

days_to_appt - days between booking date and appointment.
day_of_appt - day of the week of the appointment.
day_of_scheduling - day of the week of the booking date.
month_of_appt - month of the year of the appointment.
month_of_scheduling - month of the year of the booking date.
hour_of_scheduling - hour of the day during which the appointment booking took place. (Actual appointment time was not provided.)

## 4. Exploratory Analysis

No-shows make up approximately 20% of the data, while 80% of appointments were attended.

Correlations of features vs labels:
Labels                 1.000000
days_to_appt           0.186231
SMS_received           0.126431
prior_no_shows         0.078592
hour_of_scheduling     0.060697
Scholarship            0.029135
day_of_scheduling      0.006020
day_of_appt            0.001165
Alcoholism            -0.000196
high_temp             -0.001033
PatientId             -0.001461
impeachment_vote      -0.005801
Handcap               -0.006076
rainfall              -0.014748
Diabetes              -0.015180
visit_freq            -0.016729
prior_visits          -0.020710
month_of_appt         -0.020886
Hipertension          -0.035701
Age                   -0.060319
month_of_scheduling   -0.160862
AppointmentID         -0.162602

## 5. Model Selection
Models were tried with LOG, Random forests, SVC, and KNN.
None of the models above had very high scores for precision and recall. Given this fact, what made sense for our case was to focus on maximizing precision (at the expense of recall). Acheving high scores for both is difficult given the weakness of our dataset. However, we were able to maximize one over the other.

To do this we implemented a voting clasifier to maximize our precision.

Best individual model precision was 0.4

Voting calssifier precision is around 0.6


## 6. Predicition and final mode

Our final Coting classier model has a precision of 0.75 on the test set, which was even better than the score ont he trainign set.


## Conclusions and Recommendations

This model can predict whether or not patients are going to show up to their appointments with a 80% accuracy & 75% precision by using the above features.

The clinic can send our extra reminders to those patients or model rpedicts will be no shows. This will help minimize costs for the clinic.

Although this model still can be improved, this is a good score given the following:

1)Weak dataset with extrmeely low feature correlations vs label (correlation less than 0.1 for most features)

2)very poor individual model scores (less than 0.4 precision for most)



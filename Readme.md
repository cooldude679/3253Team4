###1.Introduction
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
The original features of interest in this dataset are;

Patient Gender

ScheduledDay - date and time of when the appointment booking was done.

AppointmentDay - date (without time) that the appointment was scheduled for.

Patient Age

Neighbourhood - neighbourhood that the clinic is located in. All neighbourhoods are in the city of Vitoria, Brazil.

Scholarship - binary feature indicating whether the patient is on a particular Brazilian social assistance program. The data source provides this wikipedia article as further explanation - https://en.wikipedia.org/wiki/Bolsa_Fam%C3%ADlia.

Hipertension, Diabetes and Alcoholism - binary features indicating whether the patient suffers from any of these conditions.

Handcap - numerical feature (from 1 to 4) indicating degree of physical disability.

SMS_received - binary feature indicating whether a text reminder was received by the patient.

No-show - binary feature indicating whether or not the patient missed their appointment.

Creating new time-related features;

days_to_appt - days between booking date and appointment.

day_of_appt - day of the week of the appointment.

day_of_scheduling - day of the week of the booking date.

month_of_appt - month of the year of the appointment.

month_of_scheduling - month of the year of the booking date.

hour_of_scheduling - hour of the day during which the appointment booking took place. (Actual appointment time was not provided.)

## 4. Exploratory Analysis

No-shows make up approximately 20% of the data, while 80% of appointments were attended.


## 5. Model Selection
None of the models above had very high scores. Given this fact, what makese sense for our business scenario would be to focus on maximizing precision (at the expense of recall). Acheving high scores for both is difficult given the weakness of our dataset. However, we may be able to maximize one over the other.
Our voting classifier was able to come up with precision score (0.6) much higher than any of the individual models.

Best individual model precision was 0.4

Voting calssifier precision is around 0.6


## Conclusions and Recommendations

This model can predict whether or not patients are going to show up to their appointments with a 80% accuracy & 75% precision by using the above features.

Although this model still can be improved, this is a good score given the following:

1)Weak dataset with extrmeely low feature correlations vs label (correlation less than 0.1 for most features)

2)very poor individual model scores (less than 0.4 precision for most)

-link textThe final model has a 0.75 precision but a very low recall. This means the model will not recall the majority of no shows. But the No shows we do predict wil be done with 75% precision.

-The implication for the hospital is that they can afford to schedule extra patients to fill in no shows with fairly high trust of our no show predidiction (75%)

-To encourage people to commit to their appointments, clinics should send them SMS reminders or some other form of reminder. Some people have busy lives and may have forgotten about their appointments, especially if they made the appointments months in advance.

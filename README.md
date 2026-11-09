# Introduction
This repository contains code for a Attendance analytics starter, using machine learning algorithms. 
The model aims to introduce grouped aggregation and simple predictive thinking.
Through grouped aggregation, attendance records are summarized into clear measures indicators for student engagement.

# Objectives
The project addresses the challenge of monitoring and predicting student engagement in virtual classrooms. While attendance logs capture raw participation data, they don’t provide actionable insights. Educators need automated tools to flag low-engagement students and anticipate disengagement trends to intervene early.


# About the Dataset

The dataset used for training and evaluation is stored in the file df_clean.csv. 
It consists of students virtual learning logs, such as student_id (Unique identifier for each student), session_id (Unique identifier for each session), join_time and leave_time (Timestamps of attendance) and duration_minutes (Computed session duration).
<img width="915" height="524" alt="image" src="https://github.com/user-attachments/assets/34d1595f-3b37-45cf-b906-9831aa7ca38e" />


# Code Files

The code is written in Python and divided into sections.

**1. Data Preprocessing and Exploration**

In this section, the dataset is loaded, explored, and preprocessed. Missing values are removed.
Timestamps (i.e join_time, leave_time) are converted into proper datetime format.
Computed duration of attendance (session durations) are derived by subtracting join time from leave time. 
Additional fields are derived, such as date and day of week and  hour features.
The dataset is split into independent variables and the target variable.

**2. Derived Variables for feature engineering :**
   Informative variables for the machine learning models are derived as:
   
   sessions_attended: Number of sessions attended per student
   
   avg_duration_min: Average session duration per student
   
   attendance_rate_pct: Percentage of sessions attended
   
   low_engagement_flag: Rule-based indicator of disengagement
   
 
**3. AI flagging feature: Median-Based Dynamic Thresholds was adopted**

Thresholds are redefined as dataset medians:

• 	Attendance Threshold = 1.2% (median attendance rate)

• 	Duration Threshold = 88.9 minutes (median session duration)


**4 ML Model**

 Random Forest Classifier Model was adopted using features: 
 
 sessions_attended,
 
 avg_duration_min,
 
 and attendance_rate_pct to target low_engament_flag. 
 
 Model was evaluated with Train/test split and 5-fold cross-validation, using various performance metrics such as accuracy, precision, recall, and F1 score.

# Key Take-Aways
<img width="1079" height="665" alt="image" src="https://github.com/user-attachments/assets/c9d6830c-7725-48d7-9737-56e99deff240" />
<img width="1150" height="666" alt="image" src="https://github.com/user-attachments/assets/0b9dc6d6-2de6-4eba-8bd7-7d1429a73a80" />
<img width="1255" height="692" alt="image" src="https://github.com/user-attachments/assets/50d7663f-7d6f-452a-a842-7da19eb32deb" />

 ***The project successfully automated engagement monitoring and demonstrated predictive modeling. 
 Future work could incorporate temporal features (e.g., attendance streaks, variability in duration) to move beyond rule replication and enable early disengagement prediction.***
 
 ***The project also demonstrates that engagement analysis must go beyond attendance counts. By combining metrics like session duration, attendance rate, and flagging logic, the system provides a clear, actionable picture of student behavior. This give     educators a data-driven foundation to intervene early, reward consistent engagement, and optimize scheduling for better outcomes.***

# Strategic recommendations
**Schedule critical sessions on Wednesday, Tuesday, or Saturday.**
**Provide support or interventions for flagged students to improve engagement.**
**Consider lighter or catch‑up sessions on Sunday/Monday to balance attendance.**

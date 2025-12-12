
This repository contains code for a Attendance analytics starter using machine learning algorithms. The model aims to introduce grouped aggregation and simple predictive thinking.
Through grouped aggregation, attendance records are summarized into clear measures indicators for student engagement.

Dataset
The dataset used for training and evaluation is stored in the file df_clean.csv. It consists of students virtual learning logs, such as student_id (Unique identifier for each student),
session_id (Unique identifier for each session), join_time and leave_time (Timestamps of attendance) and duration_minutes (Computed session duration).

Code Files
The code is written in Python and divided into sections.

1. Data Preprocessing and Exploration In this section, the dataset is loaded, explored, and preprocessed. Missing values are removed. Timestamps (join_time, leave_time) are converted into proper datetime format.
Computed duration of attendance(session durations) by subtracting join time from leave time. 
Derived additional fields such as date and day of week and  hour features.sorized, and the dataset is split into independent variables and the target variable.

2. Derived Variables are:
   sessions_attended: Number of sessions attended per student
   avg_duration_min: Average session duration per student
   attendance_rate_pct: Percentage of sessions attended
   low_engagement_flag: Rule-based indicator of disengagement
   
3. Feature Engineering: Informative variables for the machine learning models were derived as:
   sessions_attended: Number of sessions attended per student
   avg_duration_min: Average session duration per student
   attendance_rate_pct: Percentage of sessions attended
   low_engagement_flag: Rule-based indicator of disengagement 
   
4. AI flagging feature: Median-Based Dynamic Thresholds was adopted
• 	Thresholds redefined as dataset medians:
• 	Attendance Threshold = 1.2% (median attendance rate)
• 	Duration Threshold = 88.9 minutes (median session duration)

5. Random Forest Classifier Model using features: sessions_attended, avg_duration_min, attendance_rate_pct to target low_engament_flag. Model was evaluated with Train/test split and 5-fold cross-validation. Model was evaluated using various performance metrics such as accuracy, precision, recall, and F1 score.


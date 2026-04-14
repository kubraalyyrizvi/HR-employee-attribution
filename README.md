🧑‍💼 IBM HR Analytics — Employee Attrition

Predicting why employees leave, using the IBM HR Analytics dataset.


📌 Project Overview
This project analyzes employee attrition using the IBM HR Analytics dataset. The goal is to identify key drivers behind employee turnover and build a predictive model to flag at-risk employees.
Target Variable: Attrition (Yes / No)

📂 Dataset
PropertyValueSourceIBM HR Analytics (Kaggle)FileWA_Fn-UseC_-HR-Employee-Attrition.csvRows1,470 employeesFeatures35 columnsMissing ValuesNoneClass ImbalanceYes — 83.9% No, 16.1% Yes

⚠️ Dropped / Useless Features
Three columns are constants and carry zero predictive value — drop them immediately:
ColumnReasonEmployeeCountAlways 1Over18Always YStandardHoursAlways 80

📊 Key Insights
Overall Attrition Rate

16.12% of employees left — roughly 1 in 6.
Dataset is imbalanced; handle with SMOTE, class weights, or stratified splits.


🔥 Overtime is the Biggest Red Flag
OverTimeAttrition RateNo10.4%Yes30.5%
Employees doing overtime are 3x more likely to leave. This is the single strongest binary signal in the dataset.

💼 Job Role Matters Enormously
Job RoleAttrition RateSales Representative39.8%Laboratory Technician23.9%Human Resources23.1%Sales Executive17.5%Research Scientist16.1%Manufacturing Director6.9%Healthcare Representative6.9%Manager4.9%Research Director2.5%
Sales Representatives leave at nearly 40% — almost 1 in 2. Senior/director roles are stable.

🏢 Department Breakdown
DepartmentAttrition RateSales20.6%Human Resources19.0%Research & Development13.8%

💰 Income Gap is Stark
AttritionMean Monthly IncomeNo$6,833Yes$4,787
Employees who left earned ~$2,000/month less on average. Lower pay = higher flight risk.

🧍 Marital Status
StatusAttrition RateSingle25.5%Married12.5%Divorced10.1%
Single employees leave at more than double the rate of divorced ones.

✈️ Business Travel
Travel FrequencyAttrition RateNon-Travel8.0%Travel_Rarely15.0%Travel_Frequently24.9%
Frequent travellers burn out — nearly 1 in 4 leaves.

🎂 Age
AttritionMean AgeNo37.6Yes33.6
Younger employees (avg. 33–34) are more likely to leave — likely early-career job hopping.

📅 Tenure
AttritionMean Years at CompanyNo7.4 yearsYes5.1 years
Employees who leave tend to have shorter tenure — the first few years are the danger zone.

😊 Job Satisfaction
Score (1=Low, 4=High)Attrition Rate122.8%216.4%316.5%411.3%
Clear trend — lower satisfaction = higher attrition. Score 1 employees leave at double the rate of score 4.

⚖️ Work-Life Balance
Score (1=Bad, 4=Best)Attrition Rate131.2%216.9%314.2%417.6%
Score 1 (worst balance) has the highest attrition — 31.2%. Interestingly, score 4 is slightly higher than 3, possibly due to overconfident job hoppers.

📈 Stock Options
LevelAttrition Rate0 (None)24.4%19.4%27.6%317.6%
No stock options = much higher attrition. Even level 1 cuts it dramatically.

🚗 Distance from Home
AttritionMean DistanceNo8.9 kmYes10.6 km
Small but consistent — employees farther from the office are slightly more likely to leave.

🚻 Gender
GenderAttrition RateMale17.0%Female14.8%
Minor difference — gender alone is not a strong predictor.

🧠 Top Predictors (Summary)
Based on EDA, these are the most important features to include in any model:

OverTime — strongest binary signal
MonthlyIncome — significant income gap
JobRole — Sales Rep vs Director gap is huge
StockOptionLevel — no options = high risk
Age — younger employees leave more
MaritalStatus — single employees leave more
JobSatisfaction — clear inverse relationship
WorkLifeBalance — score 1 is a red flag
BusinessTravel — frequent travel = burnout
YearsAtCompany — early tenure is risky
DistanceFromHome — mild but consistent signal


🛠️ Tech Stack

Python
Pandas, NumPy
Matplotlib, Seaborn
Scikit-learn


🚀 How to Run
bashgit clone https://github.com/yourusername/hr-attrition
cd hr-attrition
pip install -r requirements.txt
jupyter notebook

📁 Project Structure
hr-attrition/
│
├── data/
│   └── WA_Fn-UseC_-HR-Employee-Attrition.csv
│
├── notebooks/
│   └── EDA.ipynb
│   └── Model.ipynb
│
├── README.md
└── requirements.txt

📜 License
Dataset sourced from IBM HR Analytics on Kaggle. For educational use only.

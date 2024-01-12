# Call_Centre_Trends_PwC
## Introduction
This project aims to create a Power BI dashboard that reflects all relevant Key Performance Indicators (KPIs) and metrics in the dataset. 

Possible KPIs include:

- Overall customer satisfaction

- Overall calls answered/abandoned

- Calls by time

- Average speed of answer

- Agent’s performance quadrant
## Data Preparation
The data was loaded into Power BI Desktop and transformed in the Power query editor. 
## Data Process
- Created a new table for measures.
## Data Analysis
The following measures were created using DAX:
-     Total Calls = COUNT(Call_Center_Dataset[Answered (Y/N)]) 
-     Calls answered = CALCULATE(COUNT(Call_Center_Dataset[Answered (Y/N)]), FILTER(Call_Center_Dataset, Call_Center_Dataset[Answered (Y/N)] = "Y"))
-     Calls unanswered = CALCULATE(COUNT(Call_Center_Dataset[Answered (Y/N)]) , FILTER(Call_Center_Dataset, Call_Center_Dataset[Answered (Y/N)] = "N"))
-     Calls resolved = CALCULATE(COUNT(Call_Center_Dataset[Resolved]), FILTER(Call_Center_Dataset, Call_Center_Dataset[Resolved] = "Y"))
-     Calls unresolved = CALCULATE(COUNT(Call_Center_Dataset[Resolved]), FILTER(Call_Center_Dataset, Call_Center_Dataset[Resolved] = "N"))
-     Avg Satisfaction Rate = CALCULATE(AVERAGE(Call_Center_Dataset[Satisfaction rating]), FILTER(Call_Center_Dataset, NOT ISBLANK(Call_Center_Dataset[Avg Talk Date])))
-     Avg speed of answer in sec = CALCULATE(AVERAGE(Call_Center_Dataset[Speed of answer in seconds]), FILTER(Call_Center_Dataset, NOT ISBLANK(Call_Center_Dataset[Avg Talk Date])))
## Data Visualization

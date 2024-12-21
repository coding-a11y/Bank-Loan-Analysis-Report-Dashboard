# Bank-Loan-Analysis-report-using-Power-BI-Dashboard

### Dashboard Link :https://app.powerbi.com/links/ahwg1jIuWr?ctid=a1a4ee51-99fa-437d-8ba7-d05192f6c077&pbi_source=linkShare

## Problem Statement


This dashboard helps the bank understand its loan applicants better. It enables the bank to evaluate customer satisfaction with their loan services, identify areas for improvement, and enhance their overall service quality. Through various metrics and feedback ratings, the bank can pinpoint specific issues that may be contributing to customer dissatisfaction.

The dashboard also highlights key insights into loan processing times and approval delays. By identifying bottlenecks or inefficiencies, the bank can address these issues to provide a more streamlined experience for customers.

Since the proportion of neutral or dissatisfied applicants (almost 57%) is higher than satisfied applicants (around 43%), the bank should prioritize improving customer service and loan processing efficiency.

Additionally, with an average delay of 15 minutes in loan application approval or disbursement, it is essential for the bank to focus on reducing these delays to improve customer satisfaction and retention.

Steps Followed for Bank Loan Analysis Dashboard Creation
Load Data into Power BI Desktop:
The dataset, provided as a CSV file, was imported into Power BI Desktop for analysis.
Data Profiling in Power Query Editor:
Opened the Power Query Editor.
Enabled the following options under the View tab in the Data Preview section:
Column Distribution
Column Quality
Column Profile
Changed the Column Profiling settings to analyze the entire dataset (default profiling is limited to the first 1000 rows).
Data Observation:
Reviewed all columns for errors and missing values.
Found no errors or empty values except in the column Approval Delay.
Handling Null Values for Delay Calculation:
Excluded null values in the Approval Delay column while calculating the average delay time, as they constituted less than 1% of the data.
Theme Selection:
Selected a theme for the report under the View tab in the report view to enhance its visual appeal.
Adding Visuals for Ratings:
Added a visual to represent ratings using the three ellipses in the Visualizations Pane in the report view.
Filters for Key Fields:
Added slicers (visual filters) for the following fields:
Loan Type
Customer Type
Branch Location
Application Type
Card Visuals for Key Metrics:
Added two card visuals to the canvas:
One showing the average loan processing delay (in minutes).
Another showing the average loan approval delay (in minutes).
Used the Visual Level Filter in the Filters Pane to exclude null values when calculating averages (although blank values are ignored by default during average calculations).
Bar Chart for Customer Feedback:
Added a bar chart to represent the number of satisfied, neutral, and unsatisfied applicants.
Included the Gender field in the Legend bucket to segment feedback by gender.
Ratings Visual for Key Performance Indicators (KPIs):
Used the Ratings Visual to depict feedback on the following parameters:
Loan Disbursement Time
Customer Support
Application Process Clarity
Ease of Online Loan Application
Loan Information Transparency
Interest Rate Competitiveness
Loan Repayment Options
Branch Assistance
Mobile App Functionality
Approval Notification Process
Loan Amount Customization
Processing and Approval Convenience


Here’s a tailored version of your content, rewritten for a bank loan report:

Bank Loan Application Analysis Report
Report Summary:
This report analyzes customer feedback and operational data for bank loan applications to help improve services and customer satisfaction. The report was created in Power BI Desktop and subsequently published to Power BI Service. Key insights, metrics, and ratings were derived to assist the bank in identifying areas for improvement.

Metrics and Calculations:
Step 1: Loan Parameters and Average Ratings
Key parameters affecting customer satisfaction were identified and analyzed. Some parameters were assigned a value of 0, representing non-applicability for certain customers. These values were excluded when calculating average ratings.

The following parameters and average ratings were recorded:

Loan Disbursement Time: 3.63/5
Customer Support: 3.31/5
Application Process Cleanliness: 3.29/5
Ease of Online Loan Application: 2.88/5
Loan Information Transparency: 3.21/5
Interest Rate Competitiveness: 3.36/5
Loan Repayment Options: 3.64/5
Online Support Services: 2.81/5
Branch Assistance: 3.37/5
Mobile App Functionality: 3.38/5
Approval Notification Process: 3.33/5
Loan Amount Customization: 3.44/5
Processing and Approval Convenience: 3.22/5
Step 2: Key Visualizations Added to the Dashboard
Bank Name and Tagline: Displayed using text boxes.
Logo: Inserted as an image for branding.
Age Group Segmentation: A calculated column was created to group customers by age using the following DAX expression:
DAX
Copy code
Age Group = 
IF(loan_application_data[Age]<=25, "0-25 (25 included)",
IF(loan_application_data[Age]<=50, "25-50 (50 included)",
IF(loan_application_data[Age]<=75, "50-75 (75 included)",
"75-100 (100 included)")))
Step 3: Total Count of Customers
A measure was created to count the total number of loan applicants:

DAX
Copy code
Count of Customers = COUNT(loan_application_data[ID])
The total number of applicants was 129,880, represented via a card visual.

Step 4: Customer Distribution by Type
Using the DAX measure below, percentages of applicants were calculated for different loan types:

DAX
Copy code
% Customers = (DIVIDE(loan_application_data[Count of Customers], 129880)*100)
Step 5: Total Loan Amount Disbursed
To calculate the total loan amount disbursed:

DAX
Copy code
Total Loan Amount = SUM(loan_application_data[Loan Amount])
Insights from the Dashboard:
1. Total Applicants
Total Number of Applicants: 129,880
Satisfied Applicants (Male): 21.68%
Satisfied Applicants (Female): 21.76%
Neutral/Unsatisfied Applicants (Male): 27.58%
Neutral/Unsatisfied Applicants (Female): 28.97%
Thus, a higher percentage of applicants are neutral or dissatisfied.
2. Average Ratings
Ratings for various parameters affecting customer satisfaction were calculated. Notable areas for improvement include:

Ease of Online Loan Application (2.88/5)
Online Support Services (2.81/5)
3. Applicant Segmentation
Age Groups:

21.69% of customers are in the "0-25" age group.
52.44% of customers are in the "25-50" age group.
25.57% of customers are in the "50-75" age group.
0.31% of customers are in the "75-100" age group.
Customer Type:

First-time applicants: 18.31%
Returning customers: 81.69%
Loan Purpose:

Business Loans: 69.06%
Personal Loans: 30.94%
4. Average Delays
Average processing delay: 15.09 minutes
Average approval delay: 14.71 minutes
Recommendations:
Improve Ease of Online Loan Application: Focus on streamlining the digital interface and simplifying the application process.
Enhance Online Support Services: Provide real-time chat options and better query resolution.
Reduce Delays: Focus on optimizing loan approval workflows to reduce processing delays.
Target High-Potential Segments: Tailor marketing strategies toward the 25-50 age group and returning customers, who form the majority of applicants.

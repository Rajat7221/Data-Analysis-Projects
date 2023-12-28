# Overview
The "RBC Bank Customer Churn Analysis" is a real -time Power BI Data Analysis Project,sourcing the real data provided by DataVizon. It aims to provide valuable insights into customer churn within the RBC bank. By exploring various data attributes, the analysis seeks to understand the factors influencing customer decisions to leave the bank. The ultimate goal is to facilitate churn prevention strategies, enabling the development of effective loyalty programs and retention campaigns. 

## Business Requirements
### Data Dictionary
- **RowNumber:**
  - Corresponds to the record (row) number and has no effect on the output.
- **CustomerId:**
  - Contains random values and has no effect on customer leaving the bank.
- **Surname:**
  - The surname of a customer has no impact on their decision to leave the bank.
- **CreditScore:**
- Can influence customer churn. Categorized as:
  - Excellent: 800–850
  - Very Good: 740–799
  - Good: 670–739
  - Fair: 580–669
  - Poor: 300–579.
- **Geography:**
  - A customer’s location can affect their decision to leave the bank.
- **Gender:**
  - Explores whether gender plays a role in a customer leaving the bank.
- **Age:**
  - Relevant, as older customers are less likely to leave their bank than younger ones.
- **Tenure:**
  - Refers to the number of years that the customer has been a client of the bank.
- **Balance:**
  - A good indicator of customer churn. People with a higher balance are less likely to leave.
- **NumOfProducts:**
  - Refers to the number of products that a customer has purchased through the bank.
- **HasCrCard:**
  - Denotes whether or not a customer has a credit card. 1 represents a credit card holder, 0 represents a non-credit card holder.
- **IsActiveMember:**
  - Active customers are less likely to leave the bank. 1 represents an Active Member, 0 represents an Inactive Member.
- **Estimated Salary:**
  - Like balance, people with lower salaries are more likely to leave the bank compared to those with higher salaries.
- **Exited:**
  - Whether or not the customer left the bank. 0 represents Retain, 1 represents Exit.
- **Bank DOJ:**
  - Date when the customer associated/joined with the bank.

### Data Gathering
Data for the analysis was gathered from the following data assets:
- ActiveCustomer
- Bank_Churn
- CreditCard
- CustomerInfo
- ExitCustomer
- Gender
- Geography

## Churn Analysis- PROBLEM STATEMENT
The analysis focuses on understanding customer churn and extracting actionable insights. By examining patterns within the data, the project aims to answer key questions about the factors influencing a client's decision to leave the company. The insights obtained will inform the development of loyalty programs and retention campaigns.

# Key Findings:

The analysis of the "RBC Bank Customer Churn" data has revealed several key findings:

1. **Credit Scores and Churn:**
   - Customers with "Fair" credit score are more likely to exit.

2. **Geographic Influence:**
   - Geographic location may influence customer churn.The churn rate in GERMANY is 97.75% higher than average churn rate of France and Spain.

3. **Age and Tenure Impact:**
   - Age and tenure play a significant role in customer retention.

4. **Product Ownership:**
   - The number of products owned play a less significant role in churn likelihood.

5. **Active vs. Inactive Members:**
   - Active members tend to stay more loyal compared to inactive members.

These findings provide valuable insights that can inform targeted strategies for customer retention and churn prevention.


## Project Execution Steps
1. **Requirement Gathering (BRD / FRD):**
   - Gathered business requirements to define the scope and objectives of the analysis.
2. **Data Gathering (Database / CSV/ Excel):**
   - Collected data from various sources, including databases and CSV/Excel files.
3. **Data Cleaning / Data Transformation:**
   - Cleaned and transformed the data to ensure accuracy and consistency.
4. **Data Modelling:**
   - Created data models to represent relationships and structures within the dataset.
5. **Designing UI:**
   - Designed a user interface for the PowerBI report, ensuring clarity and user-friendly navigation.
6. **Writing DAX (based on business logic):**
   - Implemented Data Analysis Expressions (DAX) based on business logic to derive meaningful metrics and calculations.
7. **Implemented Row Level Security:**
   - Ensured data security by implementing row-level security to restrict access to specific data based on user roles.
8. **Created a workspace and provided workspace access:**
   - Organized the project by creating a dedicated workspace and managing access permissions.
9. **Publish the PowerBI Report to workspace:**
   - Published the finalized PowerBI report to the designated workspace for collaboration and sharing.
10. **Created a Dashboard and also mobile view:**
    - Developed an interactive dashboard for a comprehensive view of key metrics and insights. Ensured compatibility with mobile devices.
11. **Created an App:**
    - Developed a PowerBI app for streamlined sharing and consumption of the report.
12. **Installed on-premises Standard mode Gateways:**
    - Installed on-premises gateways to enable data refresh and connectivity with local data sources.
13. **Scheduled a refresh:**
    - Set up scheduled refresh to ensure that the data in the report stays up-to-date.
14. **Managed Alert trigger:**
    - Implemented alert triggers to notify stakeholders of specific events or thresholds.
15. **Shared the Report:**
    - Shared the PowerBI report with relevant stakeholders for review and feedback.

## Conclusion
The "RBC Bank Customer Churn Analysis" project is a comprehensive exploration of customer churn, providing actionable insights for strategic decision-making. The project showcases a structured approach, from requirement gathering to report sharing, ensuring the delivery of valuable outcomes for RBC Bank.


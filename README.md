Tools used: Power BI

# I. Project Introduction

The goal of this project is to build an interactive report which provides an overview of key operational metrics for a fictional company in the Telecommunications industry, with special focus being placed on customer churn.


# II. Key Insights 

Key insights from analysis:
  * **High-risk segment**: Customers on Month-to-Month contracts using Fiber Optic Internet show the highest churn probability.
  * **Revenue leakage**: While the churn rate is **27%**, the Revenue Loss is **31%**, indicating the company is losing its most valuable, high-tier customers.
  * **Primary churn driver**: Competition is the leading cause of exit, specifically regarding "Better Devices" and "Better Offers".



# III. Data & Architecture

The dataset contains information about a fictional telco company that provided home phone and Internet services to 7043 customers in California in Q3. 
It indicates which customers have left, stayed, or signed up for their service. 
Multiple important demographics are included for each customer, as well as a Satisfaction Score, Churn Score, and Customer Lifetime Value (CLTV) index.

Initially the data model consisted of 5 normalized tables, leading to snowflaking and inefficient relationships. 
For the purposes of the project, I transformed the model into a Star Schema by consolidating the normalized entities into a centralized fact table, along with a lookup dimension table, which improved DAX performance and report usability.

<img width="599" height="625" alt="image" src="https://github.com/user-attachments/assets/88a9b26a-520e-426a-b077-c8549dfa2236" />

# IV. Report Features

### KPI Tracking

KPIs tracked:
  * **Retention**: Total Customers, Churned Customers, Churn Rate %, Average Tenure
  * **Financial**: Average Monthly Charges, Total Monthly Revenue, Monthly Revenue Loss
    
### Technical Features

I developed a suite of DAX measures to track the company's health, utilizing measure branching to calculate complex ratios like Revenue Loss %.

Key Technical Features:
  * **Interactive bins**: Created custom Tenure and Pricing buckets to identify specific "at-risk" customer segments.
  * **Dynamic X-axis**: Integrated Field Parameters, allowing stakeholders to switch views between Tenure and Monthly Charges dynamically.
  * **Root Cause Mapping**: A Top-10 Treemap identifies the primary drivers behind customer exits, filterable by 4 demographic slicers.
  * **Revenue Impact Gauge**: A custom-formatted gauge visualizes the "bleeding" revenue relative to the total monthly recurring revenue (MRR).

 With these features, the report provides a 360-degree view of churn, enabling users to see what happened, why it happened, and what it cost the business.

 <img width="1344" height="755" alt="image" src="https://github.com/user-attachments/assets/3a9d6648-d581-408d-9a69-88b52999af44" />

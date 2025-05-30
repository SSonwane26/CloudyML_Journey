# Internship Project 2

Story of my journey as Data Analyst, complete information of my Project and my Final Presentations.

Good Morning, I am Saurabh. Today, I'm here to provide detailed information about my journey, for this project, as a data analyst at CloudyML.

### About Me
First, let me introduce myself. My name is Saurabh Sonwane, one years' experience with analytical tools. I hold a degree in mechanical engineering and have been working as a Graduate Engineer Trainee (GET) in a multinational corporation. During my tenure there, my curiosity was piqued by the world of data sciences and analytics. I embarked on a journey to learn various analysis techniques, specializing in data transformation and visualization, utilizing tools such as MS Excel and PowerBI. Additionally, I honed my programming skills in SQL and Python.

## About Project

Python [Script](https://drive.google.com/file/d/1tXyNSbmorXgB2g5lIGlwU6kc-r1ijFY4/view)

Power BI [Report](https://app.powerbi.com/view?r=eyJrIjoiOGNmMjg0ODQtZmJiOC00ODk2LTkyNWYtZmJmZmJiYmNiMmNjIiwidCI6ImRmODY3OWNkLWE4MGUtNDVkOC05OWFjLWM4M2VkN2ZmOTVhMCJ9&pageName=221354b44a8087dc3eae)

**About Company**:

OLA is India's largest ride-hailing service (Uber’s rival). Offers cabs, autos, bikes, and even electric vehicles. Book rides via OLA app (cashless or cash payment). Options: Micro, Mini, Prime, Auto, Bike, Rentals, EVs.

**Problem Statement** (why attrition is important to solve):

Recruiting and retaining drivers is seen by industry watchers as a tough battle for Ola. Churn among drivers is high and it’s very easy for drivers to stop working for the service on the fly or jump to Uber depending on the rates. As the companies get bigger, the high churn could become a bigger problem. To find new drivers, Ola is casting a wide net, including people who don’t have cars for jobs. But this acquisition is really costly. Losing drivers frequently impacts the morale of the organization and acquiring new drivers is more expensive than retaining existing ones.

**My Role**:

I am a data analyst working in the Analytics Department at Ola, focusing on driver attrition. I have been given monthly data for a segment of drivers from 2019 and 2020, containing various attributes about their engagement and performance. My goal is to build a predictive model that can determine whether a driver is likely to leave the company based on these attributes. This will help Ola take proactive measures to retain drivers and reduce attrition.

**About Dataset**:

Data Dictionary Overview
- MMMM-YY: Reporting Date (Monthly)
- Driver_ID: Unique ID for drivers
- Age: Age of the driver
- Gender: Gender of the driver (Male: 0, Female: 1)
- City: City Code of the driver
- Education_Level: Education level (0 for 10+, 1 for 12+, 2 for graduate)
- Income: Monthly average Income of the driver
- Date Of Joining: Joining date for the driver
- LastWorkingDate: Last date of working for the driver
- Joining Designation: Designation of the driver at joining
- Grade: Grade of the driver at reporting
- Total Business Value: Total business value acquired (negative indicates - cancellation/refund or car EMI adjustments)
- Quarterly Rating: Quarterly rating of the driver (1-5, higher is better)

For More Detail [File](https://github.com/SSonwane26/CloudyML_Journey/blob/main/Internship%26Placement/Project%20Two/Ola_Driver_Dataset.csv)

**Data Analysis and Exploration**:

The goal of this analysis was to understand the key factors contributing to driver attrition and identify actionable patterns that can help reduce voluntary exits. Here's how the data analysis was approached:

1. Data Overview and Initial Understanding
    * Loaded and explored a cleaned dataset containing over 13 columns, including demographics, performance metrics, income trends, employment dates, and attrition flags.
    * Identified that the column Attrition was a binary indicator where 1 represented a driver who had left the company and 0 denoted an active driver.

2. Feature Engineering
To enhance analysis and prepare for deeper insights, several new columns were engineered:
    * Total_Tenure_Months: Calculated tenure from DateOfJoining to LastWorkingDate or latest reporting month if still active.
    * Experience_Bucket: Binned total tenure into categories like <6M, 6-12M, 1-2Y, and >2Y.
    * Income_Increased and Rating_Increased: Derived binary features to track whether a driver’s income or rating improved over time.
    * Negative_Business: Created a flag for drivers generating below-average or loss-making business.
    * Standardized categorical fields like Grade, Gender, City, Joining Designation, and Income Band.

3. Univariate and Bivariate Analysis
Conducted extensive breakdown of attrition rate by multiple variables to isolate high-risk patterns:
    * Experience: Drivers with <6 months experience showed the highest attrition rate at 15.2%.
    * Income: Those in the Low income band had an attrition rate of 12.1%, nearly 3x that of Very High income drivers.
    * Performance: Drivers whose income and ratings didn’t improve had significantly higher attrition.
    * Negative Business: Drivers contributing to business losses had a 20.8% attrition rate, nearly 2.5x higher than the average.
    * Grade Levels: Grade 1 and 2 drivers were more likely to leave than higher-graded counterparts.
    * Location Impact: Cities like C17 and C2 had disproportionately high attrition rates compared to other regions.

4. Monthly Driver Movement Analysis
    * Calculated average monthly joins and exits using date fields to understand workforce churn trends.
    * Found patterns of seasonal or campaign-driven spikes in hiring or exits.

5. High-Risk Driver Profiling
    * Developed logic to classify active drivers as high-risk based on a combination of risk factors (low experience, no rating growth, low income, negative business, etc.).
    * This logic was later implemented in Power BI using calculated columns and filters for real-time tracking.

6. Key Metrics Created
    * Attrition Rate (%)
    * Average Tenure (months)
    * Monthly Join and Exit Counts
    * Risk Flags and Experience Buckets

**Report Creation**:

The report was developed in Power BI and structured into multiple focused pages to ensure stakeholders can easily navigate and interpret the findings. The entire dashboard was designed with Ola’s brand identity in mind — using black backgrounds, yellow accents, and minimalist fonts for clarity and impact.

1. Executive Summary
Purpose: To provide a snapshot of key attrition KPIs for business leaders.
    * Metrics included: Overall Attrition Rate, Active vs Exited Drivers, Average Tenure, Monthly Join/Exit Trends.
    * Visuals: Card visuals, KPI indicators, line charts.
    * Slicer: Reporting Month (for timeline control).
    * Commentary textbox added to summarize page findings at a glance.

2. Driver Profile Analysis
Purpose: To explore attrition patterns based on demographic and job-related factors.
    * Breakdown by: Age Group, Gender, Income Band, Grade, Experience Bucket.
    * Visuals: Bar charts, stacked columns, donut charts.
    * Slicer: Attrition Status.
    * Insight: Younger and less experienced drivers are leaving at a higher rate.

3. Performance & Income Impact
Purpose: To investigate how performance and earnings relate to attrition.
    * Analyzed: Rating Increase, Income Increase, and Business Value contribution.
    * Visuals: Clustered bars, comparison charts, KPIs.
    * Conditional formatting used for negative business indicators.
    * Insight: Drivers with no income or rating growth are at high risk of leaving.

4. City & Designation Trends
Purpose: To identify geographic and role-based attrition hotspots.
    * Fields used: City, Joining Designation, and Current Grade.
    * Visuals: Maps, bar charts, and heatmaps.
    * Slicers: City and Designation.
    * Insight: Certain cities and lower designations showed higher churn.

5. High-Risk Drivers
Purpose: To flag currently active drivers who match high-risk attrition profiles.
    * High-risk criteria: Short experience, low grade, no rating or income growth, negative business.
    * Visual: Tabular list of Driver IDs with their key metrics and a "High Risk" flag.
    * Filter applied to exclude already exited drivers.
    * Action-Oriented: Enables targeted retention strategies.

6. Recommendations & Actions
Purpose: To translate data findings into strategic business recommendations.
    * Content-only page (no charts).
    * Included bullet points from analysis covering: retention actions, training, incentive redesign, etc.
    * Visual: Text boxes and smart icons for quick readability.

7. Design Choices & Best Practices
    * Color Scheme: Yellow and black (aligned with Ola's brand) for consistency and impact.
    * Font Style: Clean, readable sans-serif for better legibility.
    * Navigation: Clear tab names, bookmarks, and slicers for user-friendly exploration.
    * Interactivity: Dynamic filters and slicers used extensively for personalized exploration.

This modular report design ensures that different stakeholders — whether executives, HR, or regional managers — can derive actionable insights specific to their area of interest with minimal effort.

**Insights**:

* Experience Matters:
    * Drivers with less than 6 months of experience have the highest attrition rate (~15.2%), which significantly drops as experience increases.
    * Drivers with more than 2 years of experience have the lowest attrition rate (~3.5%).

* Income Band Influence:
    * Attrition is highest among drivers in the ‘Low’ income band (~12%) and decreases steadily as income increases.
    * Drivers in the ‘Very High’ income group show the lowest attrition rate (~4.7%).

* Performance Impact:
    * Drivers who did not show any rating improvement have a significantly higher attrition rate (~8.9%) compared to those who did (~0.8%).
    * Similarly, drivers without an income increase have nearly double the attrition rate compared to those who saw growth.

* Negative Business Correlation:
    * Drivers marked with negative business value show an extremely high attrition rate (~20.8%) compared to those without (~8.3%).

* Grade Level Factor:
    * Attrition is higher among drivers with lower grades (1 and 2) and decreases with higher grade levels.

* Educational Influence:
    * Drivers with mid-level education (grade 2) show moderate attrition, while both the least and most educated show slightly higher levels.

* City-Wise Distribution:
    * Attrition rates vary widely by city, with City C17, C2, C20, and C23 experiencing the highest attrition, suggesting local conditions could be influencing factors.

* Joining Designation:
    * Higher attrition observed in drivers who joined at mid-level designations (2 and 3), potentially due to mismatch of expectations or pressure.

* Gender Gap:
    * Male and female drivers show nearly equal attrition rates, indicating gender is not a strong predictor.

**Suggestions and Recommendations**:

* Retain New Drivers More Effectively:
    * Since drivers with <6 months of experience have a 15.2% attrition rate, introduce a retention bonus of ₹2,000 at 6 months and ₹3,000 at 12 months.
    * Launch a 30-day onboarding support program to reduce early churn by at least 20% in this high-risk group.

* Incentivize Income Growth and Performance:
    * Attrition for drivers without income growth is 8.4% vs. 4.5% with growth. Introduce a tiered incentive program where a 5% monthly income growth yields bonus earnings.
    * Encourage a quarterly rating improvement goal — reward drivers who improve their rating by 0.1 or more with monthly performance incentives.

* Address Negative Business Impact:
    * With 20.8% attrition in negative business drivers, flag such drivers in a “High Risk” dashboard and assign them 1-on-1 coaching.
    * Aim to reduce this segment’s attrition to <10% within 3 months through targeted support and training.

* City-Specific Interventions:
    * Cities like C17 and C2 show attrition above 12%, while cities like C29 are below 6%. Launch pilot city programs in high-risk zones aiming to cut attrition by 25%.
    * Conduct monthly driver feedback sessions in top 5 high-risk cities to understand and act on local challenges.

* Grade-Based Upskilling:
    * Drivers with grades 1 and 2 show attrition rates of 11.4% and 9.0%, respectively. Provide training modules or in-app learning for grade improvement and track their rating and income changes.
    * Offer a “Grade Uplift” incentive for drivers who move to grade 3+ within 3 months.

* Proactive Monitoring via Dashboard:
    * Implement a High-Risk Driver Tracker that identifies drivers meeting 3 or more attrition-prone conditions (e.g., <1Y experience, no rating growth, low income).
    * Monitor this list weekly and target a 30% reduction in attrition in this segment using focused outreach.

* Monthly Feedback & Planning:
    * Introduce a Monthly Performance Review via app or SMS showing each driver’s:
        * Income growth
        * Rating change
        * Ride count
        * Personalized tips

* Encourage a goal-setting feature with gamified tracking to enhance long-term engagement.

## Acknowlegement
We've successfully concluded our project. I want to extend my gratitude to CloudyML and Team for providing me with valuable experiences and knowledge through the project. Remember, we can always learn from learning, and I'm open to receiving feedback. Let's keep growing and improving together!

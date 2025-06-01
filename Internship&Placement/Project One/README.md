# Internship Project 1

Story of my journey as Data Analyst, complete information of my Project and my Final Presentations.

Good Morning, I am Saurabh. Today, I'm here to provide detailed information about my journey, for this project, as a data analyst at CloudyML.

### About Me
First, let me introduce myself. My name is Saurabh Sonwane, one years' experience with analytical tools. I hold a degree in mechanical engineering and have been working as a Graduate Engineer Trainee (GET) in a multinational corporation. During my tenure there, my curiosity was piqued by the world of data sciences and analytics. I embarked on a journey to learn various analysis techniques, specializing in data transformation and visualization, utilizing tools such as MS Excel and PowerBI. Additionally, I honed my programming skills in SQL and Python.

## About Project

Python [Script](https://github.com/SSonwane26/CloudyML_Journey/blob/main/Internship%26Placement/Project%20One/Porter_Report_inNoteBook.pdf)

**About Company**:

Porter is India’s leading intra-city logistics platform, specializing in hyperlocal deliveries for restaurants and businesses. By connecting customers with delivery partners in real-time, Porter enables fast, efficient transportation of goods within urban areas. The company’s technology-driven approach focuses on optimizing last-mile delivery to improve customer experiences and operational efficiency.

**Problem Statement**:

* Porter needed to predict accurate delivery times for food orders by analyzing:
* Restaurant-specific factors: Cuisine type, prep time variability, and order volume.
* Logistics constraints: Fluctuations in delivery partner availability and peak-hour demand surges.
* Order characteristics: Item count, price range, and protocol (e.g., app vs. call-in orders).

**My Role**:

1. Data Analysis: Processed 200K+ order records to uncover trends in delivery times.
2. Feature Engineering: Created metrics like partner_utilization_rate and peak_hour_flag.
3. Insight Generation: Pinpointed bottlenecks (e.g., 2–4 AM partner shortages, slow cuisines).
4. Strategic Recommendations: Proposed dynamic pricing, partner incentives, and restaurant collaborations.

**About Dataset**:

The dataset includes the following information for each order:
1.	market_id: Integer ID for the market where the restaurant is located
2.	created_at: Timestamp at which the order was placed
3.	actual_delivery_time: Timestamp when the order was delivered
4.	store_primary_category: Category of the restaurant
5.	order_protocol: Integer code value for the order protocol (e.g., through Porter,call to restaurant, pre-booked, third-party, etc.)
6.	total_items: Total number of items in the order
7.	subtotal: Final price of the order
8.	num_distinct_items: Number of distinct items in the order
9.	min_item_price: Price of the cheapest item in the order
10.	max_item_price: Price of the most expensive item in the order
11.	total_onshift_partners: Number of delivery partners on duty when the order was placed
12.	total_busy_partners: Number of delivery partners attending to other tasks
13.	total_outstanding_orders: Total number of orders to be fulfilled at that moment

For More Detail [zipfile](https://github.com/SSonwane26/CloudyML_Journey/blob/main/Internship%26Placement/Project%20One/Porter_Dataset.csv)

**Data Analysis and Exploration**:

1. Data Preprocessing
    * Handled Missing Data: Imputed nulls in store_primary_category with "unknown", dropped invalid timestamps.
    * Fixed Anomalies:
        * Clipped negative values in min_item_price, total_onshift_partners.
        * Capped outlier orders (total_items > 20 deemed unrealistic).
    * Feature Engineering:
        * Derived key metrics-
            * delivery_duration = (actual_delivery_time - created_at) / 60
            * available_partners = dtotal_onshift_partners - total_busy_partners
            ... etc.

2. Exploratory Data Analysis (EDA)
    * Temporal Trends:
        * Discovered 2–4 AM had 54% longer deliveries than daytime (via boxplots by hour).
        * Weekends (Sat/Sun) accounted for 30% of total orders but 40% of delays.
    * Restaurant Impact:
        * Used ANOVA to confirm cuisine type (store_primary_category) significantly affected prep time (p < 0.01).
        * Top 3 slowest cuisines: Caribbean (56 mins), Belgian (55 mins), Spanish (54 mins).
    * Partner Utilization:
        * Scatterplots revealed delivery times spiked when available_partners_ratio < 0.2.
        * 2 AM had 59 busy partners (peak) but only 9 available (critical shortage).

3. Statistical & Correlation Analysis
    * Key Correlations:
        * total_outstanding_orders vs. delivery_duration: *r = 0.62* (strong positive).
        * available_partners_ratio vs. delivery_duration: *r = -0.45* (moderate negative).
    * Outlier Detection:
        * Used IQR to flag orders with:
            * Delivery time > 120 mins (top 1%).
            * Subtotal > ₹20,000 (bulk orders needing special handling).

**Insights**:

1. Demand Patterns
    * Peak Hour Surge: Orders between 1–4 AM (especially weekends) saw 54+ min deliveries – 30% slower than off-peak times.
    * Weekend Spike: Saturdays had 8,580 orders (highest volume) with 20% longer delivery times vs. weekdays.
    * Late-Night Focus: 2 AM was the busiest hour (1,306 orders), but with the fewest available partners.

2. Operational Bottlenecks
    * Partner Shortages: When available partners dropped below 5, delivery times spiked to 51+ mins (vs. avg. 45 mins).
    * Restaurant Delays:
        * Caribbean/Belgian cuisines took 56 mins (vs. 45 mins avg.) due to longer prep times.
        * Orders with >10 items averaged 98 mins (vs. 40 mins for single-item orders).
    * Inefficient Protocols: Protocol 6 orders took 59 mins (vs. 41 mins for Protocol 7).

3. Market Disparities
    * Market 1 had the slowest deliveries (50.3 mins), while Market 2 was fastest (45.7 mins).
    * Market 6 had 50% fewer orders than other markets, suggesting underutilized capacity.

**Suggestions and Recommendations**:

1. Optimize Partner Allocation *(Target: Reduce peak-hour delays by 20%)*
    * Incentivize Late-Night Shifts: Offer +25% bonus pay for partners working 1–4 AM weekends.
    * Dynamic Throttling: Pause new orders when:
        * Available partners < 5
        * Outstanding orders > 50
    * Cross-Market Balancing: Redirect 15% of partners from Market 6 to Market 1 during peaks.

2. Improve Restaurant Efficiency (Target: Cut prep time by 15%)
    * Prep-Time Agreements: Partner with slow restaurants (Caribbean/Belgian) to:
        * Pre-chop ingredients during 6–8 PM pre-peak.
        * Implement real-time readiness alerts for dispatch.
    * Bulk Order Surcharge: Add 10% fee for orders >10 items to offset delays.

3. Enhance Demand Planning (Target: Shift 10% of peak demand)
    * Off-Peak Discounts: Offer 15% off for 6–10 AM orders to balance load.
    * Transparent ETAs: Show dynamic estimates (e.g., "2 AM: 50–60 mins | 5 AM: 40 mins").

4. Protocol & Process Upgrades
    * Deprecate Protocol 6: Migrate users to faster channels (e.g., Protocol 3: 45 mins avg.).
    * Real-Time Alerts: Flag orders exceeding 45 mins for manual intervention.

## Acknowlegement
We've successfully concluded our project. I want to extend my gratitude to CloudyML and Team for providing me with valuable experiences and knowledge through the project. Remember, we can always learn from learning, and I'm open to receiving feedback. Let's keep growing and improving together!

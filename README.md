# Optimizing Customer Engagement at MTA NYCT: A Data-Driven Approach

## Project Overview

This project delves into the MTA New York City Transit (NYCT) Customer Engagement Statistics from 2017 to 2022. Leveraging a comprehensive dataset, this analysis aims to identify key factors influencing customer service performance, particularly focusing on "Average Time to Answer (s)" and "Calls Answered Rate." By understanding these dynamics, I can propose actionable insights to enhance MTA's customer experience and operational efficiency.

**My core objective is to answer critical business questions such as:**
* What is the relationship between call wait times and the rate of answered calls?
* Are there trends or patterns in customer engagement metrics over time?
* How can data-driven insights be used to improve customer satisfaction and operational workflows at MTA NYCT?

## Business Problem & Impact

In any service-oriented organization, customer satisfaction is paramount. For a public transit agency like MTA NYCT, efficient and responsive customer service directly impacts public trust and ridership. Long wait times and a low call answered rate can lead to frustrated customers, negative perceptions, and potentially deter ridership. This project addresses these challenges by providing a quantitative understanding of customer engagement, allowing for targeted interventions to improve service quality.

**Key business insights derived from this analysis can help MTA NYCT to:**
* **Optimize Staffing Levels:** Understand peak call times and resource requirements to ensure adequate staffing.
* **Improve Training Programs:** Identify areas where call center agents might need additional training to reduce average handling times.
* **Enhance Customer Satisfaction:** By reducing wait times and increasing call resolution rates.
* **Strategic Planning:** Use historical data to forecast future demands and proactively address potential bottlenecks.

## Dataset

The analysis utilizes the "[MTA NYCT Customer Engagement Statistics_2017-2022](data/MTA_NYCT_Customer_Engagement_Statistics__2017-2022.csv)" dataset. This dataset includes various metrics related to customer interactions, such as:
* `Date`
* `Call Type`
* `Total Calls Received`
* `Calls Answered`
* `Calls Abandoned`
* `Avg Time to Answer (s)`
* `Calls Answered Rate` (calculated)
* `Abandon Rate` (calculated)

The dataset provides a rich source of information to understand the performance of MTA's customer service operations over a five-year period.

## Methodology

This project employs a data-driven approach, primarily using Python with libraries like Pandas for data manipulation and Scikit-learn for statistical modeling. All visualizations and dashboards were created using Power BI.

The key steps I involved are:

1.  **Data Loading & Preprocessing:** I loaded the CSV data, handled missing values, and ensured data types are appropriate for analysis.
2.  **Exploratory Data Analysis (EDA):**
    * I analyzed trends in various engagement metrics over time.
    * I identified correlations between different metrics.
    * I visualized distributions and relationships to uncover patterns. All visualizations were created in Power BI.
3.  **Feature Engineering (if applicable):** I created new features from existing ones to enhance model performance or provide deeper insights.
4.  **Statistical Modeling:** (Based on my `MTA_NYCT.ipynb` file, I used Linear Regression).
    * I built a linear regression model to predict `Calls Answered Rate` based on `Avg Time to Answer (s)`.
    * I evaluated the model's performance and interpreted the coefficients to understand the impact of wait times.
5.  **Insights & Recommendations:** I translated technical findings into clear, actionable business recommendations.

## Analysis and Key Findings


Here are the key findings from my analysis, with each point corresponding to a distinct visualization:

* **Figure 1: Executive Summary Dashboard**
    * This dashboard provides a high-level snapshot of MTA NYCT’s customer engagement performance across channels.
    * Total Incoming Calls were ~4.16M, of which 3.49M were answered, resulting in an average 85% call answer rate. While this is decent, it still means ~624K calls were missed, indicating potential operational improvements.
    * Help Point Activations totaled ~3.63M, with an excellent average response time of ~11.4 seconds, reflecting strong on-ground responsiveness.
    * Social Media Satisfaction Score averaged ~3.7 (out of 5), showing generally positive public sentiment with room for improvement.
    * Overall, while Help Points perform excellently and social media is satisfactory, the call center shows significant missed call opportunities for service enhancement.
      
    ![Executive Summary Dashboard](images/Executive_summary.jpg)

* **Figure 2: Customer Engagement Traffic Across Channels**
    * Understanding how customers reach out is crucial. Figure 3 provides a breakdown of customer engagement traffic across various channels (e.g., calls, social media, help points), highlighting customers prefer to ask queries over call the most, whereas least on social media. Also, after 2019 number of queries decreased drastically because of COVID-19.
      
    ![Customer Engagement Traffic Across Channels](images/Traffic_over_chnannels.jpg)

* **Figure 3: Call Center Performance Overview**
    * The line chart shows an inverse trend between Calls Answered Rate and Avg Time to Answer. As average wait times increased from ~150s in 2017 to ~350s in 2022, answer rates declined from ~93% to ~78%.
    * The scatter plot quantifies this relationship, indicating a strong negative correlation – when average wait time exceeds 300s, answer rates fall below 80%, highlighting the criticality of reducing wait times for better service.
    * The bar chart compares Total Incoming Calls vs Calls Answered per year. Even during low-demand Covid years, a consistent 10-20% gap remains, implying persistent operational limitations.
      
    ![Call Center Performance Overview](images/Call_center_performance.jpg)

* **Figure 4: Social Media Engagement Trends**
    * Mentions peaked in 2019 (~600K) with agency responses increasing proportionally, followed by a decline post-Covid to ~200K mentions in 2022.
    * Customer Satisfaction Score rose sharply from single digits in 2017 to ~45 in 2020, with a slight decline thereafter, suggesting good but plateauing satisfaction.
    * The scatter plot reveals no strong direct correlation between number of responses sent and satisfaction score, implying that quality of responses drives satisfaction more than quantity.
    * Overall, investing in response quality, tone, and resolution effectiveness will have greater impact than merely increasing response volumes.
      
    ![Social Media Engagement Trends](images/Socialmedia_engagement.jpg)

* **Figure 5: Help Point Service Usage and Effectiveness**
    * Help Point Activations peaked in 2018 (~900K) but declined by ~66% to ~300K by 2022. While Covid impacted usage, continued decline suggests shifting customer preferences or reduced footfall.
    * Average response time, however, has steadily increased from ~9.7s in 2017 to ~14s in 2022.
    * Despite declining usage, slower responses indicate operational inefficiencies. Maintaining quick response standards is essential to ensure customer safety and confidence in Help Points as a reliable              channel.
      
    ![Help Point Service Usage and Effectiveness](images/Help_point_service.jpg)

* **Figure 6: Written Customer Feedback & Response Metrics**
    * The bar chart shows Written Responses Sent consistently exceeding Written Feedback Received across years, indicating proactive outreach.
    *	Feedback peaked in 2019 (~80K) and declined post-pandemic, suggesting customers are moving towards digital or real-time channels.
    *	The gauge shows ~540K total written responses sent, highlighting significant resource allocation to this channel.
    * The takeaway is that while proactive written responses build trust, monitoring customer channel preferences will optimize resourcing.
      
    ![Written Customer Feedback & Response Metrics](images/Written_feedback_response.jpg)

* **Figure 7: Alerts and Service Notice Impact on Customer Engagement**
    * Displays, Web, and Service Emails/Text Alerts remain the dominant channels, indicating high reliance on digital communication.
    *	Posters and Elevator/Escalator alerts have minimal usage, suggesting either low operational focus or user uptake.
    *	Total alerts peaked in 2019 (~350K) and declined since then, reflecting service and operational adjustments during the pandemic.
    * This analysis helps prioritize channel investments towards digital platforms while evaluating the need to strengthen underutilized channels like elevator/escalator alerts for accessibility compliance.
      
    ![Alerts and Service Notice Impact on Customer Engagement](images/Alerst_and_service_notice.jpg)

* **Figure 8:  Call Volume Forecasting and Prediction Results**
    * The model forecasts calls stabilizing around ~300K per year, with a wide confidence interval reflecting forecast uncertainty.
    *	Historical decline from ~950K in 2018 to ~300K in 2022 is projected to flatten, but external factors like service changes or digital adoption could shift demand significantly.
    * For planning, the baseline can guide resource allocation while the wide confidence band suggests regularly updating forecasts with new data.
      
    ![Call Volume Forecasting and Prediction Results](images/Forecasting.jpg)

## Business Recommendations

Based on my analysis, here are actionable recommendations for MTA NYCT:

1.  **Prioritize Reducing Average Time to Answer:** This is the most critical factor influencing the `Calls Answered Rate`. Invest in technologies or processes that streamline call routing, provide self-service options, or optimize agent workflows to reduce wait times.
    * **Implement Interactive Voice Response (IVR) Systems:** To significantly reduce the average call waiting time, I recommend implementing or enhancing IVR systems. This would automate responses to frequently asked questions and efficiently route complex inquiries, freeing up agents for more critical issues.
2.  **Targeted Training for High-Impact Call Types:** Develop specialized training for agents handling call types identified with consistently long wait times (e.g., service disruptions, complex inquiries). This could improve resolution rates and reduce call durations.
3.  **Dynamic Staffing Models:** Implement a dynamic staffing model that adjusts agent availability based on historical call volume patterns (e.g., seasonal peaks, specific days/hours with high call loads).
4.  **Implement Feedback Mechanisms:** Continuously gather customer feedback on call waiting times and agent performance to identify areas for continuous improvement.
5.  **Explore Self-Service Options:** For common inquiries, consider enhancing digital self-service options (FAQs, chatbots, mobile app features) to deflect calls and reduce overall call volume, thereby decreasing wait times for more complex issues.
6.  **Leverage LLMs for Social Media Engagement:** To reduce wait times and improve responsiveness on social media, I recommend utilizing Large Language Models (LLMs). LLMs can perform real-time sentiment analysis to quickly identify and prioritize critical negative feedback, enabling rapid and targeted responses to enhance customer satisfaction.

## Technical Details

* **Programming Language:** Python (for EDA and forecasting)
* **Libraries Used:**
    * `pandas`: For data manipulation and analysis.
    * `numpy`: For numerical operations.
    * `sklearn.linear_model.LinearRegression`: For building the linear regression model.
* **Visualization Tool:**
    * `Power BI`: For creating interactive dashboards and all visualizations (all screenshots included in this README are derived from Power BI).
* **Notebook:** `MTA_NYCT.ipynb` contains the full code for data loading, preprocessing, EDA, and model building.


## Future Enhancements

* **Time Series Forecasting:** Implement time series models (e.g., ARIMA, Prophet) to forecast future call volumes and average wait times, enabling proactive resource allocation.
* **Integration of Large Language Models (LLMs):** Explore using LLMs for more advanced sentiment analysis of qualitative feedback (e.g., from written feedback, social media, or potential call transcripts), automated response generation for common queries, and intelligent routing of customer inquiries to further enhance engagement and efficiency.
* **Deep Dive into Abandoned Calls:** Analyze the characteristics of abandoned calls to understand why customers drop off and develop strategies to mitigate this.
* **Interactive Dashboards (Advanced):** Enhance existing Power BI dashboards or create new ones with more interactive features and drill-down capabilities for deeper exploration by stakeholders.

## Contact

Yash Garg - linkedin.com/in/yg98 - yashgarg9099@gmail.com

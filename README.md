# Customer Segmentation & Retention ROI Analysis

## Business Question
Which customer segments deliver the highest ROI on retention campaigns, and how should a marketing team allocate a limited retention budget across them?

## Approach
- Cleaned ~1 million transaction records from the UCI Online Retail II dataset (removed cancellations, missing customer IDs, and invalid values), leaving 805,549 clean transactions across 5,878 customers.
- Built an RFM (Recency, Frequency, Monetary) model per customer using pandas.
- Scored and segmented all customers into 8 groups: Champions, Loyal Customers, At Risk (High Value), Can't Lose Them, New Customers, Needs Attention, Others, and Lost.
- Built an Expected ROI model per segment using estimated reactivation success rates and a per-customer campaign cost assumption.
- Built an interactive dashboard (HTML/JS + Chart.js) with a live budget allocator.

## Key Finding
"At Risk (High Value)" customers deliver the highest retention ROI, followed by Champions and "Can't Lose Them." The largest segment by customer count, "Lost," delivers the lowest ROI and should receive minimal retention spend despite its size — a naive "target the biggest group" strategy would misallocate budget.

## Recommendation
Prioritize retention budget toward At Risk (High Value) and Can't Lose Them segments, where historical value is high but engagement is declining. Use light-touch loyalty communication (not discount-heavy campaigns) for Champions, since they are already active. Minimize spend on Lost and Others segments, where expected returns are lowest.

## Tools
Python (pandas), Jupyter Notebook, HTML/JavaScript, Chart.js

## Files
- `rfm_analysis.ipynb` — full analysis code, from data cleaning to ROI modeling
- `rfm_segments.csv` — customer-level RFM scores and segment labels
- `segment_summary.csv` — segment-level summary statistics and ROI
- `rfm_dashboard.html` — interactive dashboard with budget allocator

## Live Dashboard
   https://manvigupta0027-cyber.github.io/rfm-customer-segmentation/rfm_dashboard.html

## Limitations
- Reactivation success rates are estimated assumptions, not measured from an actual A/B test, and should be validated with a real campaign pilot before scaling budget.
- Expected value saved uses historical total spend as a proxy for future customer value.

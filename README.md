# E-Commerce Data Analytics: Courier and Order Performance

## Project Overview
This project evaluates e-commerce operations with a primary focus on order fulfillment, courier performance, and refund rates. Using Python, the analysis assesses three major couriers (Arrow, Bolt, Cyclone) across various product categories and regions to provide quantitative, data-driven recommendations for a single courier logistics strategy. 

## Dataset
The analysis integrates three relational datasets:
* `orders.csv`: Contains transactional records including order date, customer ID, geographic region, product category, and total order value.
* `shipments.csv`: Tracks parcel-level fulfillment data including the assigned courier, dispatch date, delivery date, transit status, and shipping duration.
* `refunds.csv`: Logs financial return events, capturing the refund date, categorical reason (e.g., Damaged, Late, Wrong Item, Customer Cancelled), and refunded amount.

## Methodology
* **Data Integration:** Shipment, order, and refund datasets are merged to establish a unified base for calculating net revenue and adjusted return rates at the parcel level.
* **Performance Aggregation:** Group-level metrics are computed to identify fulfillment bottlenecks and top revenue drivers by category, region, and courier.
* **Statistical Hypothesis Testing:** * **Two-Proportion Z-Test:** Deployed to determine the statistical significance of the difference in refund rates between the highest and lowest performing product categories.
  * **ANOVA (Analysis of Variance):** Utilized to verify if shipping transit times significantly differ among the three couriers.

## Key Results
* **Logistics Speed:** Cyclone operates as the fastest courier with an average shipping duration of 1.74 days, outperforming Arrow (2.53 days) and Bolt (3.50 days). The ANOVA test yielded a p-value of 0.0, confirming the statistical significance of these speed differences.
* **Quality of Service:** Arrow delivers the most reliable service, resulting in the lowest adjusted refund rate (5.37%) and the lowest overall bad outcome rate (11.20%) when excluding customer-initiated cancellations.
* **Category Performance:** Electronics drive the highest total order value and net revenue. Conversely, Clothing experiences the highest refund rate (9.06%), while Home goods record the lowest (7.06%). A two-proportion Z-test between these categories yielded a z-statistic of 1.756 (p-value = 0.079).
* **Profitability:** The operational combination of the Arrow courier delivering Electronics generated the highest net revenue per parcel at $114.18.

## Repository Structure
* `analysis.ipynb`: The core Jupyter Notebook containing the data wrangling pipeline, exploratory data analysis, statistical testing, and courier selection strategy.
* `orders.csv`: The primary e-commerce sales dataset.
* `shipments.csv`: The logistics and delivery tracking dataset.
* `refunds.csv`: The returns and financial adjustments dataset.

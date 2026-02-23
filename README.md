# Online Retail Analytics Dashboard: A Strategic Overview

This README provides a comprehensive overview of the Online Retail Analytics Dashboard project, detailing its objectives, methodologies, key findings, and actionable recommendations. Developed to transform raw transactional data into strategic business intelligence, the dashboard offers a multi-faceted view of customer behavior, product performance, and operational efficiency within an e-commerce context. The insights derived are crucial for informed decision-making, ranging from marketing campaign optimization to inventory management and loss prevention.

## Project Overview

**Topic Chosen**: The project focuses on analyzing online retail transactional data to understand customer behavior, product performance, and operational efficiency. This topic was chosen due to its direct applicability in e-commerce, offering valuable insights for strategic business growth and optimization.

**Question Addressed**: The dashboard addresses critical business questions such as: What are the key revenue trends? How are customers segmented and retained? What are the primary drivers of returns and operational losses? How does country-level performance vary?

## Data Source

The analysis utilizes the `online_retail_II.xlsx` dataset, containing transactional data from a UK-based online retail store. The dataset covers two years (December 2009 to December 2011) and includes details like invoice number, product description, quantity, unit price, customer ID, and country.

## Steps & Methodology

### Data Cleaning and Transformation

Raw data from two Excel sheets was combined. Key steps included:

- **Column Standardization**: Renaming `Customer ID` to `CustomerID` and `Price` to `UnitPrice`.

- **Data Type Conversion**: Ensuring `Quantity` and `UnitPrice` are numeric, and `InvoiceDate` is a datetime object.

- **Cancellation Handling**: Identifying and flagging cancelled transactions (invoice numbers starting with 'C' or negative quantities). These rows were **removed** from core revenue analyses to ensure accurate metrics, but retained for specific returns analysis.

- **Feature Engineering**: Calculating `Revenue` (`Quantity * UnitPrice`), `InvoiceMonth`, and `InvoiceYear`.

- **Filtering**: Excluding non-product `StockCode` values (e.g., 'DOT', 'POST') from product-level analyses.

### Analysis Approach

The methodology involved:

- **Revenue Analysis**: Examining monthly and yearly revenue trends, and identifying top-performing products.

- **RFM Segmentation**: Categorizing customers based on Recency, Frequency, and Monetary values to understand customer lifetime value and behavior.

- **Cohort Analysis**: Tracking customer retention rates over time to identify seasonal impacts and churn patterns.

- **Returns Analysis**: Differentiating between customer-initiated returns (product quality signal) and operational losses (warehouse write-offs) to pinpoint root causes.

- **Country Performance**: Analyzing revenue, orders, and customer metrics by geographical region.

### Tool Selection and Design Decisions

The dashboard is built using **Streamlit** for its interactive web application capabilities, allowing for rapid deployment and ease of use for non-technical stakeholders. **Pandas** was used for data manipulation, and **Plotly Express** for generating interactive visualizations. Custom CSS was applied to create a consistent and professional dark theme.

## Dashboard Screenshots

### Revenue Overview:

![Revenue Overview Dashboard Screenshot](https://private-us-east-1.manuscdn.com/sessionFile/5zVI0TxmKnCrz2zh0l7wFS/sandbox/heWTQy9qDzn4UFHFqDCl9y-images_1771861012420_na1fn_L2hvbWUvdWJ1bnR1L3VwbG9hZC9wYXN0ZWRfZmlsZV8wbG9FQ29faW1hZ2U.png?Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cHM6Ly9wcml2YXRlLXVzLWVhc3QtMS5tYW51c2Nkbi5jb20vc2Vzc2lvbkZpbGUvNXpWSTBUeG1LbkNyejJ6aDBsN3dGUy9zYW5kYm94L2hlV1RReTlxRHpuNFVGSEZxRENsOXktaW1hZ2VzXzE3NzE4NjEwMTI0MjBfbmExZm5fTDJodmJXVXZkV0oxYm5SMUwzVndiRzloWkM5d1lYTjBaV1JmWm1sc1pWOHdiRzlGUTI5ZmFXMWhaMlUucG5nIiwiQ29uZGl0aW9uIjp7IkRhdGVMZXNzVGhhbiI6eyJBV1M6RXBvY2hUaW1lIjoxNzk4NzYxNjAwfX19XX0_&Key-Pair-Id=K2HSFNDJXOU9YS&Signature=ERSz9-NY8hHX6JejbNQeMQakLwFXl9qNEWLIWXqiGuuoUEB1IMzhUhPOFIrpR6v50b5iHafm46SrXsy0olmQnQ2K6Ht47FzJRKVkBxiRlHjsoXFKn-TsRu4HQgDzhR07nNTe717up5wHi0wt65UzMaALjQ7Nvu4WOOp8GUsr69KsXnFNobHuiG0V5ik~D8r1YIucETuJwM2c~Li1JXZqd7Dw9o~tZX0bZNmshGFeu0FMWTUVzzi3h6cORL6c4XQWTne033yAWeh2c-iTk2XxxDtYuTZviU5FGlupxWhVlZD15RP1Bm5kffWyMmzEaakMN8WaxAXv3V166fdcmTgNvA__)

### RFM Customer Segmentation:

![RFM Customer Segmentation Dashboard Screenshot](https://private-us-east-1.manuscdn.com/sessionFile/5zVI0TxmKnCrz2zh0l7wFS/sandbox/heWTQy9qDzn4UFHFqDCl9y-images_1771861012420_na1fn_L2hvbWUvdWJ1bnR1L3VwbG9hZC9wYXN0ZWRfZmlsZV9lWlVFeHRfaW1hZ2U.png?Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cHM6Ly9wcml2YXRlLXVzLWVhc3QtMS5tYW51c2Nkbi5jb20vc2Vzc2lvbkZpbGUvNXpWSTBUeG1LbkNyejJ6aDBsN3dGUy9zYW5kYm94L2hlV1RReTlxRHpuNFVGSEZxRENsOXktaW1hZ2VzXzE3NzE4NjEwMTI0MjBfbmExZm5fTDJodmJXVXZkV0oxYm5SMUwzVndiRzloWkM5d1lYTjBaV1JmWm1sc1pWOWxXbFZGZUhSZmFXMWhaMlUucG5nIiwiQ29uZGl0aW9uIjp7IkRhdGVMZXNzVGhhbiI6eyJBV1M6RXBvY2hUaW1lIjoxNzk4NzYxNjAwfX19XX0_&Key-Pair-Id=K2HSFNDJXOU9YS&Signature=ArCarySXADdK~M1dblLNQrScnQT1wGQqAD0A7zxQgqb4FPktcB10jGt3dmNVnoKLLLjaqVJoMQA9nnExbJuVC~SYz0Kf8RZSE0j78Z9bPf4FuOjZY0WhY-wwjnE4xSL64017GV9YEmhLntwI7GIMoqRU8uJJ4VTRFlH6~U3d9NgQAHbmcb0bcf3R2T~NEfFp1Bv45KNxsp2mMqjgOM~QpCL~9VJEIu3wpE75dwvgWpn9TZ4dsbXc181A846gXX2wIDwQOzvmhfHrPKN0faj28po~H2WNjg1QZucDxBBR641eHtCkgfx810cbtepGckt6AU8mIEsAawFtRkxmAo5MEw__)

### Cohort Retention:



![](https://private-us-east-1.manuscdn.com/user_upload_by_module/feedback/310519663377070349/aJIgtuzdLQnayFeA.png?Expires=1803399998&Signature=GB19cjwcPsArbTqwjI9-iNnOBX9p3K80VPRgCK6A56im6b9THbcuY1sN9YiXXdGYAPIINB6e2vJQsGbESgfMxrJwhYiFNNtUjJgrJPKyy8s4kXedsB2tKGbIPdF~mN3yQKk8hhbE0GqkLqyJgcq0h9EndDmlWlHCpwLxQpkVElhr51~-FIP1Ecw19GDhCgXNXac7kZuZZUXcxV1zR8ab9gtpIZeaoyVyUoFqJlMcb3GiGb-d7S12oJ6p1JafofKcpR1Uu0y~9r3KoLN0WDV4vmyZCQ6dAv3fRiulNYqneRCfwlmdeT-s618Zm~YbwOfnXy1W0nD2N23pwI6fszUuRg__&Key-Pair-Id=K2HSFNDJXOU9YS)

### Return Analysis :

![](https://private-us-east-1.manuscdn.com/user_upload_by_module/feedback/310519663377070349/fPRPyYbapHTaGHPH.png?Expires=1803397880&Signature=VDpSb9b~d1u5GAT3djixPtwiGQHyoV7PMgh0SEfogONF6jbbP-Ga50ktWwvCT5ChYa3bPMVTGTKtbN6eq-WZ3-wyTySnQZ86V0voVxEg9iHvq0hcocriIwJmz7RF8ic9CWCH8yFvXzikER3FWM93VLszggNLGitqgpDqMcmnuOCRgRMDI3j771CMmOczptr-hlBIQQhfolBrNrLy40ASvaXD96BHWiQ304p6aupDUbNdRjBFjfAMw62f2muiK3v5FTj1S1Wv~T2az8M56W~9c7vJW59-eV5pICA6EMAguJI3aqU1hOCVV8BisEjgVzNQ4nRf3xjswmxOgAwrjqRoog__&Key-Pair-Id=K2HSFNDJXOU9YS)



![](https://private-us-east-1.manuscdn.com/user_upload_by_module/feedback/310519663377070349/hosSENWBRuTOuBMf.png?Expires=1803397925&Signature=AaNgNOXyIGSx6ErRWIhWVcjTCqcof~~A4S~0g9D1C78~OJanfkNv~RM~cFUeE~XEzzSLqW3WG1aN1TtJP03w6RcQu1E1oIqXynw86rEo8qzHvf4kofJ-bFMD4ApY1vmf-0pqDfF18rhGxQUUzt~14TKhd7TJ7QWUByZJvITI-0-AZyCOpPiUS9O7SqhPokUVljwRupOR3eytqlIjfqIkkr4yDytX-d2R-mTmOk1bN9f3Bm3j0J9mfr8M7jbOKUAXpFRGMTbx5EEVgpqYkwPtpa9uaYMDHVikRfae-s95OBnlIxJevOD33aeI8IPj4bcVDO~n3GYvRBHLSlHJcz~hHA__&Key-Pair-Id=K2HSFNDJXOU9YS)



### Country performance :

![](https://private-us-east-1.manuscdn.com/user_upload_by_module/feedback/310519663377070349/pNByDzXnIddUnfkE.png?Expires=1803397961&Signature=dVVXziSGTNiUUs6luBUZIfD4qNRJuW4bi4wPq1hV4PZEa-pzFJnk7RD0NCJ4FE4bmve2C26Z5Y15U59rN0oTJrdyMgTaQvbzbr113NGzIRqsxcZIaiptpAp~7u-wnFmapBI2cEK5tHvzQ2tXuDcmK-cZi2cdNDqvyjFLk0Zdqv~Dw8M~pHvPb4eJMhBbsdaMD2ELU0J7OQXjogxLxKq5WwTM6nQvX5b4aqLaJYff6bPSeBKmSirf12qVXye9STPtJ~o34nSiqsg~BBZpgOIwEcvDMizYqUK6EGbz3TicoD1OJboUmQLRg4lpjXhaLe0Famf8mEkwYL35ZhtUhMI6pg__&Key-Pair-Id=K2HSFNDJXOU9YS)

## Design Screenshots

### Dashboard Wireframe

![Dashboard Wireframe](https://private-us-east-1.manuscdn.com/sessionFile/5zVI0TxmKnCrz2zh0l7wFS/sandbox/heWTQy9qDzn4UFHFqDCl9y-images_1771861012420_na1fn_L2hvbWUvdWJ1bnR1L3dpcmVmcmFtZQ.png?Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cHM6Ly9wcml2YXRlLXVzLWVhc3QtMS5tYW51c2Nkbi5jb20vc2Vzc2lvbkZpbGUvNXpWSTBUeG1LbkNyejJ6aDBsN3dGUy9zYW5kYm94L2hlV1RReTlxRHpuNFVGSEZxRENsOXktaW1hZ2VzXzE3NzE4NjEwMTI0MjBfbmExZm5fTDJodmJXVXZkV0oxYm5SMUwzZHBjbVZtY21GdFpRLnBuZyIsIkNvbmRpdGlvbiI6eyJEYXRlTGVzc1RoYW4iOnsiQVdTOkVwb2NoVGltZSI6MTc5ODc2MTYwMH19fV19&Key-Pair-Id=K2HSFNDJXOU9YS&Signature=D2MnZCpC6gsjB~Qq-sjB4UKhNPoX9Lyfn-MK9xmkLgvwvt4qGdodKUSyMvv6Ie2qGqADNPHPREQ8fID~Jc9jBul1qsFq1L2PyoCfMGTfSPrIbYPjlvbfOz7X2Z2k-qj4QAJn-dMvFLQN1WY1wnwPh2z~-UgMwWdYen4TaU7Pa3LZ0vNDhTusQz5MTpAN73je0zZPdYQ3vWoC-zeyUoqYjtb~gyC-pO5beBDqwRgReJVehL~ATPOTlen0syKq1bIubRXeuyqR~cQfw63lk6cCndoae40SXZ701IFKMlPJSQpwz69em9h-I8Jb3PDSVeNsr2m9DIvJY5J4DDPd-pBLZA__)

## Key Insights

This section delves into the core analytical findings derived from the processed online retail data, offering a strategic perspective on revenue trends, customer behavior, and operational aspects. Based on this, several strategic recommendations can be formulated to enhance business performance, improve customer loyalty, and mitigate operational losses:

### Revenue Performance and Product Analysis

Analysis of the loyalty customer transactions reveals a **Total Loyalty Customer Revenue of £17,452,154**, while the **Total Gross Revenue (all non-cancelled orders) stands at £20,813,918**. The **median Average Order Value (AOV) is £304.63**, which is a more representative metric than the mean AOV (£476.12) due to the skewing effect of large wholesale orders. 

Monthly revenue trends for loyalty customers show significant seasonality, with peaks typically observed towards the end of the year, particularly in November and December. However, it is important to note that the data for December 2011 is partial, ending on December 9th, which impacts the overall revenue figure for that month. The dashboard visualizes this trend, highlighting the partial data for December 2011 to prevent misinterpretation.

**Top 10 Products by Revenue** are dominated by items such as 'REGENCY CAKESTAND 3 TIER', 'WHITE HANGING HEART T-LIGHT HOLDER', and 'PAPER CRAFT , LITTLE BIRDIE'. These products consistently contribute significantly to the overall revenue, indicating strong customer demand and potential for focused marketing or inventory strategies. The dashboard provides a clear bar chart illustrating these top-performing products.

### RFM Customer Segmentation

Customer segmentation is performed using the RFM (Recency, Frequency, Monetary) model, which categorizes customers based on their purchasing behavior. This model assigns scores for how recently a customer made a purchase (Recency), how often they purchase (Frequency), and how much money they spend (Monetary). These scores are then combined to assign customers to distinct segments, each with unique characteristics and strategic implications.

The RFM scoring thresholds are dynamically derived from the dataset, ensuring that the segmentation is relevant to the specific customer base. For instance, Recency scores are categorized as follows: 4 (best) for 0–26 days, 3 for 27–96 days, 2 for 97–379 days, and 1 (worst) for >379 days. Similarly, Frequency scores range from 1 (lowest) for 1 order to 4 (highest) for >7 orders.

The dashboard presents a clear distribution of customers across various RFM segments, including:

- **Champions**: Customers with high recency, frequency, and monetary scores, representing the most valuable and loyal customers.

- **Loyal Customers**: Active customers with consistent purchasing behavior.

- **At Risk**: Customers who were historically frequent and high-spending but have become inactive.

- **Cannot Lose Them**: Customers who were once the highest-frequency buyers but are now inactive.

- **About to Sleep**: Inactive customers with low frequency, indicating a churn risk.

- **Promising**: Recently active customers with only one order so far, showing potential for loyalty.

- **Recent Customers**: Very recent first-time buyers.

- **Potential Loyalists**: Mid-range recency/frequency but solid spend.

- **Need Attention**: Customers with low scores across all three dimensions.

- **Lost**: Long-inactive customers with a single purchase, likely churned.

This segmentation allows for targeted marketing strategies, such as retention campaigns for 'At Risk' customers or loyalty programs for 'Champions'. The dashboard provides a visual representation of the customer count by segment, enabling stakeholders to quickly understand the composition of their customer base.

### Cohort Retention Analysis

Cohort analysis provides insights into customer retention over time by grouping customers based on their acquisition month. This allows for the tracking of how long customers remain active and the identification of trends or issues related to specific acquisition periods.

The analysis focuses on 3-month retention rates for each cohort. For instance, the **Dec-2010 cohort exhibited a 3-month retention rate of 9.2%**. This is notably lower than the **average 3-month retention across all cohorts, which stabilizes at approximately 21.7%** after the initial Month-1 drop-off. This disparity suggests that customers acquired during the Christmas peak (Dec-2010) are largely one-time holiday shoppers rather than organic retail customers, leading to a sharp drop in retention after the first month.

Conversely, cohorts acquired in mid-2011 show slightly stronger retention, indicating a potential improvement in customer quality or acquisition strategies during that period. This insight highlights an opportunity for reactivation campaigns, particularly in the 1-2 month window after initial purchase, to re-engage customers who might otherwise churn. The dashboard visualizes these retention trends through a heatmap, providing a clear overview of cohort performance over time.

### Returns Analysis

The dashboard distinguishes between two critical categories of returns to provide actionable insights:

- **Customer Returns (Product Quality Signal)**: These returns are initiated by customers and often indicate issues related to product quality, accuracy of description, or customer satisfaction. Analyzing these returns helps in identifying problematic products or areas for improvement in product offerings.

- **Operational Losses (Warehouse Write-offs)**: These refer to internal losses due to damaged stock, printing errors, storage conditions, or other operational inefficiencies. Understanding these losses is crucial for optimizing warehouse management, logistics, and internal processes.

**Top 10 Customer Returns** : include products like 'REGENCY CAKESTAND 3 TIER', 'BAKING SET 9 PIECE RETROSPOT', and 'STRAWBERRY CERAMIC TRINKET BOX'. A high return count for these items signals potential product quality issues or discrepancies between customer expectations and the actual product. This information can be used to engage with suppliers, refine product descriptions, or improve quality control.

**Operational Losses by Root Cause Category** reveal that 'Other' (uncategorized), 'Printing Issues', and 'Damaged Stock' are the leading causes of units lost. Specifically, 'Printing Issues' account for a significant number of lost units (28,258), followed by 'Damaged Stock' (24,077) and 'Uncategorised — needs review' (15,556). These findings suggest immediate areas for operational improvement:

- **Printing Issues**: The largest loss category, warranting an immediate investigation into the print supplier or internal printing processes.

- **Damaged Stock**: Requires consolidated tracking to identify the specific stage in the warehouse or supply chain where damage occurs.

- **Storage Issues**: Losses due to 'wet/mouldy' items point to problems with humidity control or shelving in storage facilities.

- **Uncategorized**: Vague reason codes like 'check', 'found', or 'lost' highlight the need for enforcing mandatory, specific reason codes for all operational losses to enable more precise root cause analysis.

- **Weekly Loss Monitoring**: Implementing weekly monitoring of write-offs and escalating when any category spikes by more than 20% can provide an early warning system for emerging operational issues, allowing for timely corrective actions.

### Country Performance

Geographical analysis of sales performance reveals significant variations across different countries. The dashboard provides a breakdown of revenue, orders, and customers by country, along with the Average Order Value (AOV) for each region. This allows for the identification of key markets and areas for potential expansion or focused marketing efforts.

**Top 15 Countries by Revenue** are prominently displayed, with the United Kingdom naturally leading due to the company's base of operations. Other significant contributors include Germany, France, and EIRE. Understanding the performance of these countries helps in allocating resources effectively and tailoring regional strategies. The dashboard visualizes this data through a bar chart and a choropleth map, offering both detailed and high-level geographical insights.

### Strategic Recommendations

Based on the comprehensive analysis presented in this dashboard, several strategic recommendations can be formulated to enhance business performance, improve customer loyalty, and mitigate operational losses:

#### Customer-Centric Strategies

- **Targeted Retention Campaigns**: The cohort analysis reveals a significant drop-off in retention after Month 1, especially for the Dec-2010 cohort. This suggests an opportunity for targeted reactivation campaigns in the 1-2 month window post-purchase, particularly for customers acquired during peak seasonal periods. Personalized offers or engagement strategies could convert one-time buyers into loyal customers.

- **Loyalty Programs for Champions**: The RFM segmentation identifies 'Champions' as the most valuable customer segment. Implementing exclusive loyalty programs, early access to new products, or personalized communication can further solidify their loyalty and encourage continued high-value purchases.

- **Nurturing Promising and Recent Customers**: 'Promising' and 'Recent Customers' show potential for future loyalty. Tailored onboarding experiences, follow-up communications, and incentives for a second purchase can help transition these customers into more frequent buyers.

#### Product and Revenue Optimization

- **Optimize Top-Performing Products**: The consistent high revenue generated by products like 'REGENCY CAKESTAND 3 TIER' indicates strong demand. Ensuring consistent stock levels, exploring cross-selling opportunities with complementary products, and featuring these items prominently in marketing efforts can maximize their contribution.

- **Investigate High-Return Products**: Products with high customer return rates, such as 'REGENCY CAKESTAND 3 TIER' and 'BAKING SET 9 PIECE RETROSPOT', warrant further investigation. This could involve reviewing product quality, refining product descriptions to manage customer expectations, or engaging with suppliers to address manufacturing defects.

#### Operational Efficiency and Loss Prevention

- **Address Printing Issues**: Given that 'Printing Issues' are a major contributor to operational losses, an immediate and thorough investigation into the print supplier or internal printing processes is crucial. This could involve quality audits, process improvements, or exploring alternative suppliers.

- **Streamline Damaged Stock Tracking**: The significant losses from 'Damaged Stock' necessitate a more robust tracking system. Identifying the specific points in the warehouse or supply chain where damage occurs can help implement targeted preventative measures, such as improved handling procedures or packaging.

- **Improve Storage Conditions**: Losses due to 'wet/mouldy' items point to problems with humidity control or shelving in storage facilities.

- **Enforce Mandatory Reason Codes for Returns**: The presence of 'Uncategorised — needs review' in operational losses underscores the need for mandatory and specific reason codes for all returns and write-offs. This will enable more accurate root cause analysis and targeted interventions.

- **Weekly Loss Monitoring**: Implementing weekly monitoring of write-offs and escalating when any category spikes by more than 20% can provide an early warning system for emerging operational issues, allowing for timely corrective actions.

#### Geographical Expansion and Localization

- **Leverage Strong Country Performance**: Countries with high revenue and customer engagement, such as Germany and. France, represent strong markets. Further investment in localized marketing, customer support, and product offerings in these regions can drive continued growth.

- **Explore Underperforming Regions**: For countries with lower performance, a deeper dive into market specifics, competitive landscape, and logistical challenges is recommended. This could uncover untapped potential or inform decisions to reallocate resources.

## Live Dashboard Link

Access the interactive dashboard here: [Online Retail Analytics Dashboard](https://online-retail-dashboard-38dmea9nh8jfyuvxxldima.streamlit.app/)

## Assumptions & Limitations

- **AOV Calculation**: Median AOV is used as a more robust metric due to the presence of large wholesale orders skewing the mean.

- **Generalizability**: Insights are based on data from a single UK-based online retailer and may not be directly generalizable to other businesses or markets.

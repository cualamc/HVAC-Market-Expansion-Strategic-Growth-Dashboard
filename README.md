# 📊 **HVAC Strategic Expansion & Financial Performance Dashboard**

### **Project Overview**

This project involved developing a comprehensive Power BI solution for an HVAC company to evaluate market saturation, income rankings, and regional expansion opportunities. It features a custom "Expansion Score" using the 15-year equipment death window, operational profit analysis, and geospatial market share mapping. Includes DAX-driven scoring (0-100) to identify "Defensive Retention" vs. "Growth" opportunities. The final dashboard provides strategic advisors with a data-driven framework to identify high-value zip codes and optimize resource allocation. 

---

### 🚀 **Key Features & Business Logic**

**1. Comprehensive Performance Overview**: Developed a high-level executive summary tracking core KPIs including Total Revenue, Customer Acquisition, and Job Volume. Segmented data by Job Types (e.g., Maintenance vs. Installation) and Customer Types (Residential vs. Commercial) to identify the most profitable business segments.
<img width="1428" height="802" alt="image" src="https://github.com/user-attachments/assets/388bddc0-57c5-4789-a936-ab2314662f6d" />
<img width="1428" height="799" alt="image" src="https://github.com/user-attachments/assets/8e9634d6-dbb1-43bb-af03-a031b0f04f21" />

**2. Income Ranking & Scoring**: Developed a custom scoring algorithm to rank geographic areas based on household income levels and service demand.
<img width="1427" height="801" alt="image" src="https://github.com/user-attachments/assets/f4f4ed85-b4a3-439d-bb25-f01da743b269" />

**3. Strategic Expansion Analysis**: Created a "Saturation Index" to identify under-served markets for client-style business scaling.
<img width="1426" height="799" alt="image" src="https://github.com/user-attachments/assets/b945ee35-8698-4cf5-84fb-f26180fc318b" />

**4. Efficiency in Data Extraction**: Implemented a method for extracting and cleaning Excel-based zip code estimates to ensure regional accuracy.

---

### 📈 **Strategic Insights & Case Study Findings**

**1. Operational Profitability**
  - The "Maintenance Paradox": Identified that maintenance jobs—while good for loyalty—are the least cost-efficient, taking 3 days longer than installations while yielding significantly lower revenue per ticket.
  - Revenue Concentration: Discovered the average revenue per customer is 725% higher than the median, revealing a high dependency on rare, high-value "massive sales" rather than a consistent volume-driven model.
  - Zero-Revenue Volume: Audited over 16.5k tickets to find that the median revenue per ticket was $0, highlighting a heavy lean toward "reactive" repair work.

**2. Market Expansion Logic (The Three Pillars)**

I developed a proprietary Expansion Score to evaluate new territories based on:
  1. Financial Health: Affordability metrics including Median Household Income and Unemployment.
  2. Serviceable Housing: Density of owner-occupied, single-unit residential rooftops.
  3. The "15-Year Death Window": A specialized growth metric targeting homes built between 2000–2009, where AC units are statistically likely to require full replacement.

**3. Performance-Based Segmentation**

Using a consolidated 0-100 score, ZIP codes were categorized to dictate strategy:
  - Top Performing (e.g., 70124): High market potential with "Up" revenue trends; recommended for sales model replication.
  - Underperforming: Areas with "Down" trends requiring immediate audit of lead follow-ups and staffing.
  - Overall Status: The portfolio score of 45.68 indicates a "Defensive Retention" phase, focusing on loyalty and referrals due to a <1% market share.

---

### **🛠 Technical Workflow**
**1. Data Integrity & Cleaning**

  - Temporal Auditing: Purged records where "Completion Date" preceded "Created Date" to ensure accurate velocity metrics.
  - Logic-Based Retention: Navigated inconsistent sales datasets by cross-referencing surrounding data points to maintain record integrity rather than outright deletion.
  - Optimization: Simplified complex measures to improve dashboard rendering speed and end-user responsiveness.

**2. Data Transformation (Power Query)**

To ensure high performance, I prioritized data shaping within Power Query rather than relying solely on DAX.
  - Efficient Extraction: Streamlined the ingestion of messy Excel workbooks containing population and income estimates.
  - Calculated Columns: Used Power Query for static attributes (e.g., geographic grouping) to reduce the memory footprint of the .pbix file.
  - Query Dependency & Staging Strategy: I implemented a Staging and Reference architecture to modularize the transformation process. By disabling the "Load" for intermediate queries, I minimized the memory footprint while maintaining a clear, auditable trail from raw source to final fact table.

<img width="1688" height="639" alt="image" src="https://github.com/user-attachments/assets/88502c3b-2750-4640-80ac-90e0c1b9c5b3" />

**3. Data Modeling & DAX**

The model follows a Star Schema design to support complex time-intelligence and ranking calculations.
  - Measures vs. Columns: Utilized DAX measures for dynamic calculations like Income Rank and Market Penetration %, ensuring they react correctly to slicers.
  - Scoring Logic: Wrote DAX expressions to weight different KPIs, providing a single "Opportunity Score" for each territory.

**4. Visualization & UX**

The dashboard was designed with Strategic Advisors in mind, focusing on high-level KPIs and drill-down capabilities.
  - Strategic Framework: Integrated metrics specifically tuned for expansion-focused business analysis.
  - Geospatial Analysis: Used zip code mapping to visualize financial performance and market density across service areas.

---

### 💻 **Tools & Technologies**
Power BI Desktop: Lead visualization and modeling tool.
Power Query (M): Used for ETL (Extract, Transform, Load) processes.
DAX: Used for advanced statistical scoring and ranking.
Excel: Source data for regional estimates.

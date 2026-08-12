### 📊 Interactive Dashboard View
![Dashboard View](Screenshot%202026-08-12%20095733.png)

**Description & Key Highlights:**
* **Executive Summary (KPIs):** Displays overall high-level business performance metrics:
  * **Total Sales:** $2,297,200.86
  * **Total Profit:** $286,397.02
  * **Total Orders:** 9,994
  * **Profit Margin:** 12.47%
  * **Average Discount:** 15.62%
* **Interactive Slicers:** Positioned on the left panel allowing users to dynamically filter data by **Category** (Furniture, Office Supplies, Technology), **Ship Mode**, **Region**, and **Sub-Category**.
* **Visual Insights:**
  * **Sales Per Month (Line Chart):** Tracks revenue trend over time, showing strong end-of-year seasonality (peaking in November & December).
  * **Regional & Sub-Category Performance (Bar Charts):** Identifies **West** as the leading region and **Phones** as the top revenue-generating sub-category.
  * **Return Tracking:** Visualizes return volume across main categories.
  ### 🛠️ Data Modeling & Relationships (Power Pivot)
![Data Model](Screenshot%202026-08-12%20100430.png)

**Description & Model Architecture:**
* **Data Schema:** Built a Relational Data Model (Star Schema topology) inside **Power Pivot**.
* **Table Relationships:**
  * **`Orders` (Fact Table):** Contains transaction-level order detail metrics.
  * **`Returns` (Dimension Table):** Connected to `Orders` via a **1-to-Many** relationship using `Order ID`.
  * **`Managers` (Dimension Table):** Connected to `Orders` via a **1-to-Many** relationship using `Region`.
* **Benefit:** Enables seamless cross-table filtering, accurate aggregation without duplicate entries, and optimal query performance for DAX formulas.
### 🧮 DAX Calculations & Explicit Measures
![DAX Formulas](Screenshot%202026-08-12%20100448.png)

**Description & Measure Implementations:**
* **Dynamic KPIs via DAX:** Utilized Data Analysis Expressions (DAX) in the Power Pivot Data Model to calculate complex metrics on the fly.
* **Key DAX Formulas Implemented:**
  * `Total Returned = CALCULATE(COUNT(Orders[Returned]), Orders[Returned] = "Yes")`
  * Dynamic calculation of **Average Order Value (AOV)** (`$229.86`), **Profit Margin %** (`12.47%`), and **Total Unique Customers** (`793`).
* **Feature Engineering:** Added calculated columns such as `Order Delivery (Days)` to measure shipping performance and transit duration.
### 📈 Pivot Tables & Granular Insights Breakdown
![Insights Analysis Sheet](Screenshot%202026-08-12%20100401.png)

**Description & Analytical Findings:**
* **Regional & City Performance:** Detailed breakdown revealing **West** ($725.46K) and **East** ($678.78K) as main revenue drivers, while **New York City** leads at the city level ($256.37K).
* **Product Hierarchy Analysis:** Breakdown of top vs. bottom performing categories and sub-categories (e.g., **Technology** leads with $836.15K sales; **Fasteners** generated the lowest at $3,024.28).
* **Operational Issues (Returns Analysis):** Highlighted that out of **800 total returned orders**, the **Office Supplies** category accounted for the highest share (**473 returns**), indicating potential quality control or packaging issues in that department.
  

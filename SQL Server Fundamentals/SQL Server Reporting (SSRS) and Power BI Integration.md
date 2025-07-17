# SQL Server Reporting (SSRS) and Power BI Integration

## Building and Publishing Reports via SSRS  
**Theory:**  
- SQL Server Reporting Services (SSRS) is a server-based report generating software system.  
- It allows you to create, manage, and deliver both paginated and interactive reports.  
- Reports can be deployed to a report server and accessed via web or email subscriptions.

**Hands-On:**  
- Use SQL Server Data Tools (SSDT) or Report Builder to design reports (.rdl files).  
- Connect reports to SQL Server data sources using T-SQL queries or stored procedures.  
- Deploy reports to the SSRS server via the Report Manager or Visual Studio.  
- Schedule report execution and subscription for automated delivery.

---

## Linking SQL Server to Power BI Datasets  
**Theory:**  
- Power BI connects to SQL Server databases to fetch data for visualization and analysis.  
- Power BI supports DirectQuery mode (live query) and Import mode (data load).  
- Efficient dataset design in SQL Server improves Power BI performance.

**Hands-On:**  
- In Power BI Desktop, use `Get Data > SQL Server` to connect.  
- Choose the mode (DirectQuery or Import) based on data freshness and size.  
- Use SQL views or stored procedures as data sources for better abstraction.  
- Refresh datasets on Power BI Service to keep data current.

---

## DAX Formulas for Summarization  
**Theory:**  
- DAX (Data Analysis Expressions) is the formula language in Power BI for calculations and aggregations.  
- Common functions include `SUM()`, `CALCULATE()`, `FILTER()`, and time intelligence functions like `TOTALYTD()`.

**Hands-On:**  
- Create calculated columns and measures in Power BI Desktop using DAX.  
- Example measure to sum sales:

      Total Sales = SUM(Sales[Amount])

- Example measure to calculate year-to-date sales:

      Sales YTD = TOTALYTD(SUM(Sales[Amount]), Dates[Date])

---

## Data Modelling in Power BI  
**Theory:**  
- Data modelling involves creating relationships between tables to enable effective data analysis.  
- Star schema is preferred: fact tables with measures connected to dimension tables.  
- Proper cardinality and cross-filter direction settings optimize query results.

**Hands-On:**  
- Define relationships in Power BI model view between tables on keys.  
- Set appropriate cardinality (One-to-Many, Many-to-One).  
- Use calculated tables and columns when needed for advanced modelling.  
- Manage relationships to avoid ambiguity or circular dependencies.

---

## ✅ Freelance Relevance: Building Dynamic Dashboards & BI Consulting  
- SSRS and Power BI are widely used in enterprises for reporting and business intelligence.  
- Freelancers can offer report creation, dashboard design, and BI solution consulting.  
- Skills in DAX and data modelling help deliver customized, high-value insights.  
- Integration expertise supports client needs for real-time and scheduled reporting.

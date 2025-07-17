# ETL Processes (SSIS or T-SQL Based)

## Extracting from Flat Files, APIs, Excel  
**Theory:**  
- ETL (Extract, Transform, Load) involves gathering data from multiple sources such as flat files (CSV, TXT), APIs, and Excel spreadsheets.  
- Extraction is the first step where raw data is collected before cleaning and transformation.

**Hands-On:**  
- Use SSIS Data Flow Tasks to read data from flat files and Excel sources.  
- For APIs, use Script Tasks or third-party connectors in SSIS, or T-SQL with CLR integration.  
- Example: Use Flat File Source in SSIS to extract CSV data.

---

## Data Transformation with Scripts and Lookups  
**Theory:**  
- Data transformation cleans and reshapes data (filtering, converting, aggregating).  
- Lookups are used to enrich data by matching keys from reference tables.  
- Script tasks/code can handle complex logic not supported natively.

**Hands-On:**  
- Use SSIS Lookup Transformation to join reference data.  
- Use Script Component for custom transformations using C# or VB.NET.  
- In T-SQL, use `CASE`, `JOIN`, and `CTE` for transformations.

---

## Package Design in SSIS  
**Theory:**  
- SSIS packages are workflows that define the ETL process: extraction, transformation, and load tasks.  
- Packages include control flow (tasks, precedence constraints) and data flow (transformations).

**Hands-On:**  
- Create new SSIS package in SQL Server Data Tools (SSDT).  
- Use Control Flow tab to add Data Flow tasks, Execute SQL tasks, and Script tasks.  
- Configure connections, variables, and parameters for flexibility.  
- Use logging and error handling features for reliability.

---

## Scheduling via SQL Server Agent  
**Theory:**  
- Automate ETL packages by scheduling jobs with SQL Server Agent.  
- Allows running SSIS packages or T-SQL scripts at specific times or intervals.

**Hands-On:**  
- Open SQL Server Management Studio (SSMS).  
- Under SQL Server Agent, create a new job.  
- Add job steps to run SSIS package or T-SQL script.  
- Set schedule for job execution (daily, hourly, etc.).

---

## ✅ Freelance Relevance: Automated Data Loading & Financial Report Pipelines  
- Automating ETL pipelines saves client time and reduces errors.  
- ETL skills are in high demand for financial reporting and data warehousing.  
- Freelancers can build, optimize, and maintain these pipelines for diverse industries.  
- Knowing SSIS and T-SQL ETL solutions offers flexibility in project approaches.

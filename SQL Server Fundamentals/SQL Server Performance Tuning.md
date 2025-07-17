# SQL Server Performance Tuning

## Execution Plans and Query Optimization  
**Theory:**  
- Execution plans show how SQL Server executes a query, detailing index usage, joins, scans, and sorts.  
- Query optimization involves rewriting queries or adding indexes to reduce costly operations like table scans.  
- Use `SET STATISTICS TIME ON` and `SET STATISTICS IO ON` to measure query performance.

**Hands-On:**  
- In SQL Server Management Studio (SSMS), press `Ctrl + M` before running a query to display the execution plan.  
- Look for expensive operators such as Table Scan or Key Lookup.  
- Optimize queries by rewriting or adding appropriate indexes.

---

## Index Tuning (Clustered vs Non-Clustered)  
**Theory:**  
- A **Clustered Index** defines the physical order of rows in a table; only one clustered index per table.  
- **Non-Clustered Indexes** are separate data structures that speed up searches on columns other than the clustered key.  
- Proper indexing reduces IO operations and improves query speed.

**Hands-On:**  
    CREATE CLUSTERED INDEX IX_Customers_Id ON Customers(CustomerID);
    CREATE NONCLUSTERED INDEX IX_Customers_Name ON Customers(Name);

- Monitor index usage with the dynamic management view:

    SELECT * FROM sys.dm_db_index_usage_stats WHERE object_id = OBJECT_ID('Customers');

---

## Page Life Expectancy & Wait Stats  
**Theory:**  
- **Page Life Expectancy (PLE)** indicates how long data pages remain in memory; higher values imply better memory performance.  
- **Wait Statistics** reveal where SQL Server is spending time waiting (e.g., IO, locks, CPU).

**Hands-On:**  
- Check Page Life Expectancy:

    SELECT [object_name], counter_name, cntr_value
    FROM sys.dm_os_performance_counters
    WHERE counter_name = 'Page life expectancy';

- Review wait statistics:

    SELECT wait_type, wait_time_ms, waiting_tasks_count
    FROM sys.dm_os_wait_stats
    ORDER BY wait_time_ms DESC;

---

## Statistics and Fragmentation Analysis  
**Theory:**  
- Statistics help SQL Server estimate data distribution, improving query plan choices.  
- Fragmented indexes increase IO and reduce performance.

**Hands-On:**  
- Check fragmentation:

    SELECT index_id, avg_fragmentation_in_percent
    FROM sys.dm_db_index_physical_stats(DB_ID(), OBJECT_ID('YourTable'), NULL, NULL, 'LIMITED');

- Update statistics:

    UPDATE STATISTICS YourTable;

- Rebuild or reorganize indexes to reduce fragmentation:

    ALTER INDEX ALL ON YourTable REBUILD;
    ALTER INDEX ALL ON YourTable REORGANIZE;

---

## TempDB Tuning and Memory Configuration  
**Theory:**  
- TempDB stores temporary objects and can be a performance bottleneck under heavy load.  
- Using multiple TempDB data files and configuring memory properly reduces contention and improves performance.

**Hands-On:**  
- Configure multiple TempDB files (recommended: 1 file per CPU core up to 8).  
- Monitor server memory:

    SELECT * FROM sys.dm_os_sys_memory;

---

## ✅ Freelance Relevance: Speeding Up Slow Reports and APIs  
- Tuning queries and indexes enhances client satisfaction by improving performance.  
- Critical for optimizing data-heavy reports and API endpoints.  
- Demonstrates advanced skills in delivering scalable, responsive database solutions.

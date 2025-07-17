## 9️⃣ Database Maintenance & Backup

Proper maintenance and backup strategies are critical for ensuring **database integrity, availability, and recoverability**. Freelancers offering ongoing support or disaster recovery services must master these areas.

---

### 💾 Backup Types

SQL Server supports several types of backups to meet different RTO (Recovery Time Objective) and RPO (Recovery Point Objective) needs:

#### 🔹 Full Backup
Captures the entire database.

```sql
BACKUP DATABASE ClientDB TO DISK = 'D:\Backups\ClientDB_Full.bak';
```

#### 🔹 Differential Backup
Captures changes since the last full backup.

```sql
BACKUP DATABASE ClientDB TO DISK = 'D:\Backups\ClientDB_Diff.bak' WITH DIFFERENTIAL;
```

#### 🔹 Transaction Log Backup
Captures all transactions since the last log backup (for point-in-time recovery).

```sql
BACKUP LOG ClientDB TO DISK = 'D:\Backups\ClientDB_Log.trn';
```

✅ **Best Practice**: Use a combination of full + differential + log backups based on the client’s risk tolerance and recovery requirements.

---

### 🔁 Restore Strategies

Having a backup isn’t enough — being able to **restore** quickly is key.

#### 🔁 Restore Full + Differential

```sql
RESTORE DATABASE ClientDB FROM DISK = 'D:\Backups\ClientDB_Full.bak' WITH NORECOVERY;
RESTORE DATABASE ClientDB FROM DISK = 'D:\Backups\ClientDB_Diff.bak' WITH RECOVERY;
```

#### 🔁 Point-in-Time Restore

```sql
RESTORE DATABASE ClientDB FROM DISK = 'ClientDB_Full.bak' WITH NORECOVERY;
RESTORE LOG ClientDB FROM DISK = 'ClientDB_Log.trn'
WITH STOPAT = '2025-07-17 10:30:00', RECOVERY;
```

💡 **Freelance Tip**: Offer “disaster drills” to test and document restore processes for clients.

---

### 🧪 DBCC CHECKDB (Integrity Check)

Detects corruption at the page or object level.

```sql
DBCC CHECKDB('ClientDB');
```

✅ **Best Practice**: Run weekly and alert on any failures.

---

### 📈 Index Maintenance

Fragmented indexes reduce performance. Use:

#### 🔧 Rebuild (for heavy fragmentation):

```sql
ALTER INDEX ALL ON dbo.ClientTable REBUILD;
```

#### 🔧 Reorganize (for light fragmentation):

```sql
ALTER INDEX ALL ON dbo.ClientTable REORGANIZE;
```

Automate based on fragmentation percentage thresholds (e.g., 10%–30%).

---

### ⏱️ SQL Server Agent Jobs (Scheduled Maintenance)

Automate regular maintenance tasks like backups, CHECKDB, and index rebuilds.

1. Open SQL Server Agent → Jobs  
2. Create a Job → Add multiple steps (T-SQL commands)  
3. Schedule it using a daily/weekly trigger

✅ Include alerts and email notifications using Database Mail.

---

### ✅ Freelance Relevance

Freelancers can offer:

- 🔁 Scheduled backups + restore testing  
- 🧪 Database health monitoring  
- 📈 Index & stats optimization  
- ⏰ Maintenance automation  
- 🛡️ Emergency restore during outages  

These services lead to **ongoing support retainers**, **high-value contracts**, and **DR (disaster recovery) gigs**.

---

📌 References:

- [Backup and Restore SQL Server](https://learn.microsoft.com/sql/relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases)
- [DBCC CHECKDB Guide](https://learn.microsoft.com/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)
- [Index Maintenance Best Practices](https://learn.microsoft.com/sql/relational-databases/sql-server-index-design-guide)
- [SQL Server Agent Jobs](https://learn.microsoft.com/sql/ssms/agent/sql-server-agent)


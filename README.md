Using pgbench with PowerShell for PostgreSQL Benchmarking

📌 Introduction

This guide provides step-by-step instructions on downloading, setting up, and running pgbench using PowerShell for benchmarking PostgreSQL databases(local / AWS RDS/ Azure Postgresql database).

👅 1. Download PostgreSQL Binaries (Includes pgbench)

PostgreSQL provides precompiled binaries, including pgbench.

🔗 Download Link: https://www.enterprisedb.com/download-postgresql-binaries

Choose the correct version for your OS (Windows/Linux).

Extract the archive and note the folder path (e.g., C:\pgbench\). Mostly if you are on windows, the extracted ZIP will be inside downloads (if its default download location).

📂 2. Setting Up pgbench

Locate pgbench.exe in the extracted folder and save the location for later use.

⚙️ 3. Running pgbench with PowerShell

Example: Running a pgbench Benchmark on AWS RDS PostgreSQL

$env:PGPASSWORD = "XXXXX" 
& "C:\Users\xxxxx\Desktop\xxxxxxxx\xxxxxxxx\postgresql-17.3-1-windows-x64-binaries\pgsql\bin\pgbench.exe" -h postgresqlinstancestack.cpesy4o6old1.us-east-1.rds.amazonaws.com -p 5432 -U postgres -d Stackoverflow -f "C:\Users\Abhinav\Desktop\xxxxx\xxxxxx\Fundamentals_of_Vaccum\6-b-updating-users.sql" -c 50 -j 4 -t 30


Explanation of Parameters:

-h → PostgreSQL host

-p → Port (default: 5432)

-U → Username

-d → Database name

-c 50 → 50 concurrent connections

-j 4 → 4 threads

-t 30 → 30 transactions per client


✅ 4. Troubleshooting Common Issues

🔴 Issue: relation "pgbench_branches" does not exist

Fix: Add --no-vacuum to skip automatic table initialization.


📢 Contributing

Found an issue? Feel free to submit a Pull Request or open an Issue.

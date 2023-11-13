# AWS-RDS Summary:
* Managed PostgreSQL / MySQL / Oracle / SQL Server / MariaDB / Custom
* Provisioned RDS Instance Size and EBS Volume Type & Size
* Auto-scaling capability for Storage
* Support for Read Replicas and Multi AZ
* Security through IAM, Security Groups, KMS , SSL in transit
* Automated Backup with Point in time restore feature (up to 35 days)
* Manual DB Snapshot for longer-term recovery
* Managed and Scheduled maintenance (with downtime)
* Support for IAM Authentication, integration with Secrets Manager
* RDS Custom for access to and customize the underlying instance (Oracle & SQL Server)
* Use case: Store relational datasets (RDBMS / OLTP), perform SQL queries, transactions
* If you want to check if it pays for you to switch to rds, you can check it with this [AWS Pricing Calculater]([https://pages.github.com/](https://calculator.aws/#/addService/RDSMySQL))

## RDS Backups
### Automated backups:
* Daily full backup of the database (during the backup window)
* Transaction logs are backed-up by RDS every 5 minutes
* => ability to restore to any point in time (from oldest backup to 5 minutes ago)
* 1 to 35 days of retention, set 0 to disable automated backups
* Manual DB Snapshots
* Manually triggered by the user
* Retention of backup for as long as you want
* Trick: in a stopped RDS database, you will still pay for storage. If you plan on
stopping it for a long time, you should snapshot & restore instead

## if you want to converter from on-premises database into RDS:
* Create a backup of your on-premises database
* Store it on Amazon S3 (object storage)
* Restore the backup file onto a new RDS instance running MySQL


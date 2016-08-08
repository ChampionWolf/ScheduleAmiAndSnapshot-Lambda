# ScheduleBackupLambda
This project is for developing a solution for scheduling AMI and EBS backups using AWS Lambda. Scheduling is done using CloudWatch.

# Schedule AWS Backups using Lambda

AWS is not providing any option to schedule AMI or EBS snapshot. So we have to run a server for scheduling regular EBS snapshot and AMIs scripts. AWS Lambda gives option to save our function on AWS itself and CloudWatch has an option to schedule the functions. In this project, I am trying to leverage both and achieve a perfect solution for backup using AWS native services with $0 cost !!!

###Following are the functions you have to create in Lambda
* AmiBackup
* AmiRetention
* EsbBackup
* SnapshotRetention

###You can use following tags for your instances:

* Name		                  - Any AWS supported name 
* CreateAmiBackup                 - ['y', 'yes', 't', 'true', '1']
* AmiBackupDates	          - [1-31]/Daily/[sun-sat]/[Sunday-Saturday]
* BackupWindowUTC	          - [0-23]
* AmiRetentionDays (optional)     - Any integer
* ExcludeDevices (optional)	  - /dev/sd[b-z]
* TransferAmi (optional)	  -  Future option


### You can use following tags for your EBS volumes:  

* Name	                          - Any AWS supported name 
* BackupWindowUTC                 - [0-23]
* SnapshotRetentionDays(optional) - Any integer

Schedule AmiBackup and EbsBackup hourly and retention functions weekly.

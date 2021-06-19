# DATA LAKE ETL ON AMAZON EMR
This project uses a simulated music streaming service dataset of a hypothetical company, Sparkify. The datasets consist of activity logs and songs data stored in partitioned json formats on Amazon s3. The goal is to extract the data into spark, transform the data into forms useful for analytics, then load them back into s3 storage.

# Activities Carried Out
In order to achieve this task, I 
1. created an EMR cluster with one master node (`m5.xlarge`) and two slave nodes (`m5.xlarge`), using Spark 3.1.1 (for analysis and trasformation), Hadoop 3.2.1 (for storage) and  YARN (for cluster management);
2. I enabled SSH connection to the EMR master node by including my laptop's IP in the inbound rule for SSH;
3. moved the configuration file (for S3 connection) and SSH key (for communication between the master and slave nodes) to the master node;
4. created an ETL script, `etl.py`, on the master node;
5. implemented the ETL process in the `etl.py` file;
6. ran `spark-submit etl.py` to kickstart the execution;
7. monitored the execution which lasted over 2 hours.
8. inspected the data saved in s3 and found that they conformed with my expectation.
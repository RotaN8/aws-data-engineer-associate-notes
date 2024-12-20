# Extras of all topics

- SAM is not only for API Gateway and lambda, you can also deploy S3 buckets.
- Lambda provisioned concurrency work against cold start.
- To transfer data from RDS to S3, DMS is the right option.
- If you want to detect discrepancies between diferent Databases reports, go for Glue DataBrew.
- If queries are taking too long in Redshift, it could be a data skew. You need to distribute the data evenly.
- CodeDeploy doesn't work for EMR.
- You can configure S3 notifications events to trigger lambdas and run crawlers.
- If a lambda needs to access a RDS cluster, the lambda needs to be in the same VPC and the RDS security group must grant access.
- Glue for Ray to scale AI and Python workloads.
- Crawlers need an attached AWSGlueServiceRole role.
- To analyze data in real-time use Apache Flink. With sliding window you can combine data from now and before.
- If EMR is accessing data in S3, make sure both are in the same region or you'll have high latency.
- Athena takes long because the data is split in many partitions: use Athena partition projection and Glue Data Catalog indexes to optimize the retrieval of information.
- Queries are failing in Redshift and you want to check why -> STL_ALERT_EVENT_LOG.
- You want to use Spark in Athena, you need to configure it on Athena workgroups.
- Glue Data Catalog uses resources policies for access.
- Redshift event notifications are not for data changes, but to detect cluster changes and failures.
- If you want to treat data in a small file, use Python shell and pandas.
- Amazon S3 Batch Operations allows you to perform large-scale batch operations on existing S3 objects.
- MERGE in Redshift to combine data: you can apply INSERT or UPDATE
- Which metrics from Glue appear in Cloudwatch logs insight? job progress bar, job logs, driver logs, executor logs.
- You write the S3 path on Data Lake to register the bucket. NOT THE NAME.
- Redshift streaming ingestion ingests directly from Kinesis Data Streams.
- You can directly transform JSON to Parquet using Kinesis Data Firehose.
- Many small files come from Kinesis Data Firehose, it could be due to a scaling. When the files are too big, it could be a lagging from the source.
- The DMS instance must be in the same AZ and VPC as the target.
- Quicksight has no integration with VPC Connect.
- Bucketing CTAS in Athena used when you have a column with high cardinality (many unique values), and you want to distribute the data evenly. Partitioning is used when you have a column with low cardinality (few unique values) and want to organize the data into partitions
- Kinesis Data Analitycs only supposts Kinesis Data Streams, Kinesis Data Firehose, S3.
- You have added job bookmarks but the jobs still process old data, it could be that you forgot the job.commit() or the max concurrent jobs is not 1.
- EXPLAIN ANALYZE in Athena shows execution plans.
- You must monitor Redshift authentification, logging in, connections -> audit logging for Amazon Redshift.
- You want to store data from EC2 to Redshift in real time, use Kinesis Data Firehose, not Kinesis Data Streams.
- S3 deletions go before transactions. Transactions go before deleted marks.
- SQS FIFO cannot exceed 3000 messages/s.
- You have 300 GB files in Glacier Deep Archive and need to query a portion of them once a year -> Load them to S3 Standard and use S3 Select.
- Need to encrypt each file in S3 with a different key -> one bucket and Client-Side Encryption
- IAM Database authentification is for RDS MySQL and RDS PostgreSQL.
- KCL discover new shards in Kinesis Data Streams thanks to DynamoDB and balance the load.
- If you only want to read some bytes from S3 objest, then S3 Select ScanRange and Byte Range Fetch are the right choices.
- You can limit the data scanned in Athena with workgroups.
- S3 Glacier vault to store archived sensitive data and vault lock to enforce compilance.
- UNLOAD works for Athena too.
- ORC and Parquet are both columnar, but Parquet actually supports a wider range of complex data types than ORC.
- Need to load files from S3 to Redshift, consider using staging tables and one single COPY per table.
- You want to remove duplicates from S3, think of Glue FindMatches.
- You can only use DynamoDB for KCL checkpoints, and need one table per KCL application.
- S3 is consisten for GET, PUT, LIST calls.
- DMS doesn't migrate empty tables.

# Data Analytics

## Amazon EMR

- EMR = Elastic MapReduce
- EMR helps creating Hadoop clusters (Big Data) to analyze process vast amount of data
- The cluster can be made of hundreds of EC2 instances
- Supports Apache Spark, HBase, Presto, Flink
- EMR takes care of provisioning and configuration
- Provides auto-scaling feature and integrates with spot instances
- Use cases: data processing, machine learning, web indexing, big data

## AWS Glue

- Fully-managed ETL (Extract, Transform and Load) service
- We can automate all the time consuming steps of data preparation for analytics
- Serverless, pay as you go, fully managed, in the back uses Apache Spark
- Crawls data sources and identifies data formats (schema inference)
- Provides automatic code generation if we want to customize the Apache Spark code
- Sources: Aurora, RDS, Redshift, S3
- Sinks: S3, Redshift, etc
- Glue Data Catalog: Metadata (definition and schema) of the Source Tables

## Comparison and Decision Factors
- Complexity vs. Simplicity: EMR provides more flexibility and control but requires more setup and management compared to Glue, which is more straightforward and serverless.
- Cost: EMR may be more cost-effective for transient, high-compute tasks because you can shut down resources when not in use. Glue might be better for ongoing jobs due to its serverless nature, meaning you pay only for the time your jobs run.
- Performance: EMR can be more performant for complex, compute-intensive jobs. Glue is optimized for ease of use and integration rather than raw performance.
- Maintenance: Glue requires less maintenance since it is serverless and managed by AWS, whereas EMR requires some management but is highly configurable.
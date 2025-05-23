# databricks_optimizations: what really worked for us
1. Use Job Cluster instead of interactive cluster
2. Optimize driver node size and worker node size. (we dont have to share the saem sku)
3. Set aggressive auto -termination
4. For short jobs use Serverless SQLWarehouse
5. For Dev environment go for spot instance
6. Server less jobs
7. Use better pool strategy. We started with pool per applications. Not effective. Eventually settled with Pool per runtime type . The pool is shared by multiple apps.
8. For interactive applications like API, PowerBI, Adhoc Query - go for Serverless SQL warehouse
9. For batch jobs priory of orchestration => 1. Serverless Job Cluster. 2. Job Cluster . 3. Interactive Cluster (last option)
10. Keep the runtime upto date for latest optimzation from databricks
11. Go for code optimization . have deep dive on machine performance while running the jobs.
12. For job cluster if you require parallelist use databricks workflow
13. If a query you think would be slower in any database, it would definitely be slower in databricks. Apply all database optimization techiniques that you could have done in any Relational database.

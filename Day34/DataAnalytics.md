# AWS Data Analytics Services

## What is DataAnalytics
 - **What are data analytics used for?:** Data analytics helps individuals and organizations make sense of data. Data analysts typically analyze raw data for insights and trends. They use various tools and techniques to help organizations make decisions and succeed.

## What is ETL and how it works?
- ETL stands for **"extract, transform, and load."** The process of ETL plays a key role in data integration strategies. ETL allows businesses to gather data from multiple sources and consolidate it into a single, centralized location. ETL also makes it possible for different types of data to work together.


## Data Anlytics Types
 - **What are the 5 data analytics?:** The Five Key Types of Big Data Analytics Every Business Analyst Should Know
     - Prescriptive Analytics.
     - Diagnostic Analytics.
     - Descriptive Analytics.
     - Predictive Analytics.
     - Cyber Analytics.

## Data Anlytics Types

- **Prescriptive Analytics** is a form of advanced analytics which examines data or content to answer the question “What should be done?” or “What can we do to make __ happen?”, and is characterized by techniques such as graph analysis, simulation, complex event processing, neural networks, recommendation engines,

## Diagnostic analytics
- **Diagnostic analytics** is a form of advanced analytics that examines data or content to answer the question, “Why did it happen?” It is characterized by techniques such as drill-down, data discovery, data mining and correlations.


## Descriptive Analytics
- **Descriptive Analytics** is the examination of data or content, usually manually performed, to answer the question “What happened?” (or What is happening?), characterized by traditional business intelligence (BI) and visualizations such as pie charts, bar charts, line graphs, tables, or generated narratives.

## Predictive analytics
- **Predictive analytics** is a branch of advanced analytics that makes predictions about future outcomes using historical data combined with statistical modeling, data mining techniques and machine learning. Companies employ predictive analytics to find patterns in this data to identify risks and opportunities.

## Cyber analytics
- **Cyber analytics** involve the use of algorithms, statistical analysis, behavioral analytics, machine learning, and other classes of analysis to solve cybersecurity problems in a way that traditional security controls cannot.

## Does AWS provide analytics?
- **AWS is the fastest and most cost-effective place to store and analyze data**. AWS analytics tools are purpose-built to help you quickly extract data insight using the most appropriate tool for the job, and optimized to give you the best performance, scale, and cost for your needs.


## Elastic MAP Reduce
- **What is AWS EMR?**: Amazon EMR (previously called Amazon Elastic MapReduce) is a managed cluster platform that simplifies running big data frameworks, such as Apache Hadoop and Apache Spark , on AWS to process and analyze vast amounts of data.
  
## What is difference between EC2 and EMR?
- **Amazon Elastic Compute Cloud (Amazon EC2) is a web service** that provides resizable compute capacity in the cloud.**Amazon EMR** is used in a variety of applications, including log analysis, web indexing, data warehousing, machine learning, financial analysis, scientific simulation, and bioinformatics.
     
## What is the difference between AWS glue and EMR?
- **AWS Glue** infers, evolves, and monitors your ETL jobs to greatly simplify the process of creating and maintaining jobs. **Amazon EMR** provides you with direct access to your Hadoop environment, affording you lower-level access and greater flexibility in using tools beyond Spark.

## When should I use Amazon EMR?
- **Use EMR (SparkSQL, Presto, hive) when**:
     - When you dont need a cluster 24X7.
     - When elasticity is important (auto scaling on tasks)
     - When cost is important: spots.
     - Until a few hundred TB's, In some cases PB's will work.
     - When you want to separate compute and storage (external table + task node + auto scaling)


## Is EMR better than glue?
- **AWS Glue** is a flexible and easily scalable ETL platform as it works on AWS serverless platform. But, on the other hand, **Amazon EMR** is less flexible as it works on your onsite platform. So, in short, if you have flexible requirements, and you need to scale up and down, AWS Glue is a more viable option.

## Is AWS EMR serverless?
- **Amazon EMR is not Serverless**, both are different and used for different purposes. Amazon EMR is a tool for processing Big Data whereas **Serverless** focuses on creating applications without the need for servers or building serverless.

## What is AWS Glue?
- **AWS Glue** is a serverless data integration service that makes it easy to discover, prepare, and combine data for analytics, machine learning, and application development.Users can easily find and access data using the AWS Glue Data Catalog.

## What is AWS Glue good for?
- You can use **AWS Glue to organize, cleanse, validate, and format data for storage in a data warehouse** or data lake. You can transform and move AWS Cloud data into your data store. ... This metadata is stored as tables in the AWS Glue Data Catalog and used in the authoring process of your ETL jobs.

## What is AWS Glue vs lambda?
- **Glue** can only execute jobs using Scala or Python code. **Lambda** can execute code from triggers by other services (SQS, Kaftka, DynamoDB, Kinesis, CloudWatch, etc.) vs. Glue which can be triggered by lambda events, another Glue jobs, manually or from a schedule.

## Sample DataSet
     - refer the csv files
	 
# AWS Data Flow and Services
	 - refer the data workflow  
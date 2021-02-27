# Health Insurance cross sell Vehicle Insurance: Predictive Analysis Model using Pig, Tableau and PySpark

Traditional data warehouses and relational databases could not handle the massive amounts of different kinds of data. Bigdata made this possible by providing platforms to work on various types of files/data. The distributed processing framework of Hadoop enables them to run big data applications on a clustered platform. Nowadays, many companies belong to different sectors like banking, social media, retail, healthcare using big data for analytics. Hadoop has Pig and Hive to process and analyse the data that is huge for traditional databases to handle. Apache Spark acts as a generic engine to process huge amounts of data. Furthermore, Apache provides particular environments to perform machine learning algorithms. Also, it provides many components such as SQL, Machine learning and so on, making it possible to work on Python projects using PySpark. 

In this paper, I am going to study Insurance data to predict which algorithm best suits in predicting whether a customer would be interested in vehicle insurance. Like medical insurance, for vehicle insurance also customers need to pay some amount of money to the insurance provider company. This study deals with cross sell product relationships i.e., offering a product to the existing or new customers. Hence, the company needs to know whether a customer would take vehicle insurance or not. This prediction can be done by analysing the past health insurance data of customers. Generally, if a customer has vehicle insurance, the insurance provider company will give compensation to the customer in case of unfortunate accidents. 

The data I am going to analyze is Health Insurance Cross Sell Prediction taken from Kaggle website. I have worked on the train dataset of this concept taken from Kaggle. This train dataset has around 0.4 million rows with 12 columns. The 12 attributes of the dataset include: Id, Gender, Age, Driving License, Region Code, Previously Insured, Vehicle Age, Vehicle Damage, Annual Premium, Policy Sales Channel, Vintage, Response. Each column has been described in the following Dataset section. Since there are many repetitions, mentioning the salient parts of code while discussing the data preparation process. The complete code is presented in the Appendix section github and also in the Code section. Also, the results of the salient parts are discussed in the following sections.

At the first step, set up the environments which are being used for the analysis and prediction. All the required environment installation steps are mentioned in coming sections. In this study, Hadoop was launched by following the installation steps, later successive installations of Java, Hadoop, Spark, Apache Pig and Pyspark. Along with these, Tableau has also configured. Next, pre-processing the data into Pig, which was loaded from HDFS. Second, performing data cleaning which includes checking for any NULL values, validating the input values to make sure there were no discrepancies. Also, using FILTER, GROUP, COUNT, FOREACH GENERATE, DISTINCT for further exploring and cleaning the data. Also, by using PySpark, did more analysis and cleaning. Later, we focus on the visualizations that are generated using Tableau, and understanding the relation between each attribute to one another. These visualizations help in exploring the complete data. Applying dummies to convert the categorical columns into binary classification. Finally, applying a few algorithms and comparing their fit percentage on this data. Depending on the comparison of algorithms percentage, has chosen the best fit model and performed the train test split method. Later, computed accuracy and evaluated the model.

In addition to this, discuss Apache Pig instead of Apache Hive. Next on data visualizations and machine learning algorithms. Later, discussing the attributes and their count and percentage. Following by comparing the attributes and the target variable response. Finally, the study concludes how the relation between the Response and other attributes improves the percentage of taking vehicle insurance. The results and code part will be discussed in the coming sections.

### Apache Pig
Apache Pig is an open source platform used for analysing huge datasets that contain high-level language to perform data analysis. The outstanding property of this engine is parallel execution, which makes them able to handle massive data sets. It runs on Hadoop by using both HDFS (Hadoop Distributed File System) and MapReduce. Basically, Pig is designed with two components. The primary component is Pig Latin, a high-level scripting language and the secondary is for executing these scripts using MapReduce, which performs the data computation implicitly. It can be run in local mode or mapreduce mode, which supports a distributed system. It also contains several components internally.

One of the main advantages of Apache Pig is that it provides numerous operators, through which programmers can develop necessary functions on their own for manipulating and processing the data. Along with these, it also offers several operators such as GROUP BY, FILTER, JOIN, COUNT, DISTINCT and many more to apply on the data to manipulate and process it. In addition to these, it also made it possible to work with nested data types like maps, tuples, and bags, which are being missed in MapReduce. Pig Latin is SQL-like language. Pig also provides a multi-query technique that helps in reducing the code length. At the time of execution, each Pig operator is internally converted to a MapReduce job.

### PySpark
PySpark is denoted as a combination of Python and Apache Spark. Python is a general-purpose, high level programming language whereas Apache Spark is an open source platform that has been built for speed, swift performance compared to Hadoop and streaming the analytics.

Spark uses real-time data and is well known for its speed; it uses Remote Procedure Call server to provide API to other programming languages. Pyspark provides an extensive variety of huge libraries to apply machine learning techniques and algorithms. Pyspark is a Python API for Apache Spark, it uses the simplicity of python along with the enhanced power of spark to handle the Big Data. 

Resilient Distributed Datasets (RDD) is the core of Spark framework. RDD is just like a table in a database. RDDs are immutable in nature following lazy evaluations. They can hold any type of data. In RDD, the first and foremost one Resilient is for fault tolerance, also capable of rebuilding the failed data. The second one is Distributed where data is distributed among several nodes in a cluster. The third is Dataset, that collects the partitioned data with values. RDD can be performed by two operations. They are transformations and actions. Transformations operations are to create new RDD whereas actions operations are to compute and send the output back to the driver.
Dataframe in Pyspark can be of semi-structured or structured data. Similar to the tables of relational databases, the dataframe also stores the data in the form of rows and columns. Like RDD, dataframes are also immutable, following lazy evaluations and distributed in nature. 

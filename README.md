Spark Examples
==============

# Build 

To make a jar:

```
mvn package
```

# Run and test

Upload inputfile.txt to hdfs:

```
hadoop fs -put inputfile.txt
```

To run SparkWordCount  from a gateway node in a CDH5 cluster:

```
spark-submit --class com.javachen.spark.wordcount.SparkWordCount --master local \
    spark-examples-0.0.1-SNAPSHOT.jar inputfile.txt 2
```

To run JavaWordCount from a gateway node in a CDH5 cluster:

```
spark-submit --class com.javachen.spark.wordcount.JavaWordCount --master local \
    spark-examples-0.0.1-SNAPSHOT.jar inputfile.txt 2
```

To run PythonWordCount from a gateway node in a CDH5 cluster:

```
spark-submit --master local PythonWordCount.py
```

This will run the application in a single local process.  If the cluster is running a Spark standalone cluster manager, you can replace `--master local` with `--master spark://<master host>:<master port>`.

If the cluster is running YARN, you can replace `--master local` with `--master yarn`.


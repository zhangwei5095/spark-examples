Simple Spark Application
==============

A simple Spark application that counts the occurrence of each word in a corpus and then counts the
occurrence of each character in the most popular words.  Includes the same program implemented in
Java and Scala.

To make a jar:

```
mvn package
```

Upload inputfile.txt to hdfs:

```
hadoop fs -put inputfile.txt
```

To run SparkWordCount  from a gateway node in a CDH5 cluster:

```
spark-submit --class com.cloudera.sparkwordcount.SparkWordCount --master local sparkwordcount-0.0.1-SNAPSHOT.jar inputfile.txt 2
```

To run JavaWordCount from a gateway node in a CDH5 cluster:

```
spark-submit --class com.cloudera.sparkwordcount.JavaWordCount --master local sparkwordcount-0.0.1-SNAPSHOT.jar inputfile.txt 2
```

To run PythonWordCount from a gateway node in a CDH5 cluster:

```
spark-submit --master local PythonWordCount.py
```

This will run the application in a single local process.  If the cluster is running a Spark standalone cluster manager, you can replace `--master local` with `--master spark://<master host>:<master port>`.

If the cluster is running YARN, you can replace `--master local` with `--master yarn`.


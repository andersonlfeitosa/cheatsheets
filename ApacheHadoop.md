## Apache Hadoop

This is a little cheatsheet about [Apache Hadoop](http://hadoop.apache.org).

### Start
```
hdfs namenode -format
start-dfs.sh
```

### Stop hadoop
```
stop-dfs.sh 
```

### Delete files
```
hadoop dfs -rm -r -f /directory
```
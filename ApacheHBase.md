## Apache HBase

This is a little cheatsheet about [Apache HBase](https://hbase.apache.org).

### Start
```
$HBASE_HOME/bin/start-hbase.sh 
```

### Start Shell
```
$HBASE_HOME/bin/hbase shell
```

### List tables
```
list
```

### Scan table
```
scan 'table_name'
```

### Create table
```
create 'table_name', 'columnfamily_name'
```

### Insert data
```
put 'table_name', 'row_key', 'columnfamily_name:attribute_name', 'value'
```

### Get data
```
get 'table_name', 'row_key'
```

### Drop table
```
disable 'table_name'
drop 'table_name'
```

### Truncate table
```
truncate 'table_name'
```

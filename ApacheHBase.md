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

### Scan table by partial key
```
scan 'table_name', {ROWPREFIXFILTER => 'abc'}
scan 'table_name', {STARTROW => 'abc', ENDROW => 'abd'}
```

### Scan table by field
```
scan 'table_name', { COLUMNS => 'columnfamily_name:attribute_name', FILTER => "ValueFilter(=, 'binary:value')", LIMIT => 10 }
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

### Get all versions of a row
```
get 'table_name', 'row_key', { COLUMN => 'columnfamily_name:attribute_name', VERSIONS => 5 }
```

### Config table to persist versions
```
alter 'table_name', NAME => 'columnfamily_name', VERSIONS => 5
alter 'table_name', NAME => 'attribute_name', VERSIONS => 5
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

### Count rows (from command line)
```
hbase org.apache.hadoop.hbase.mapreduce.RowCounter <tablename>
```

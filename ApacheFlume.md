## Apache Flume 


This is a little cheatsheet about [Apache Flume](https://flume.apache.org).

### Start (over http)
```
flume-ng agent -n a1 -c conf -f conf/flume-conf.properties -Dflume.root.logger=DEBUG,console
```

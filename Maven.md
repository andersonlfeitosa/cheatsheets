## Apache Maven

This is a little cheatsheet about [Apache Maven](https://maven.apache.org).

```
mvn -X -Dmaven.javadoc.skip=true -Dmaven.test.skip=true -Darguments="-Dmaven.test.skip=true -Dmaven.javadoc.skip=true" release:prepare release:perform
```

```
mvn -X release:rollback -Dmaven.javadoc.skip=true -Dmaven.test.skip=true;
```

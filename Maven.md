## Apache Maven

This is a little cheatsheet about [Apache Maven](https://maven.apache.org).

```
mvn -X -Dmaven.javadoc.skip=true -Dmaven.test.skip=true -Darguments="-Dmaven.test.skip=true -Dmaven.javadoc.skip=true" release:prepare release:perform
```

```
mvn -X release:rollback -Dmaven.javadoc.skip=true -Dmaven.test.skip=true;
```

```
mvn sonar:sonar -Dsonar.login=jenkinsic -Dsonar.password=senha -Dsonar.host.url=http://sonar.com.br
```

### Maven deploy file to Nexus 3
```
mvn org.apache.maven.plugins:maven-deploy-plugin:3.0.0-M1:deploy-file -Durl=http://nexus3.com.br/repository/my-repo-snapshots/ -DrepositoryId=my-repo-snapshots -Dfile=target/my-enforcer-maven-plugin-1.0.0-SNAPSHOT.jar -DpomFile=pom.xml
```

### Maven deploy file to Nexus 2
```
mvn org.apache.maven.plugins:maven-deploy-plugin:3.0.0-M1:deploy-file -Durl=http://nexus2.com.br/nexus/content/repositories/my-repo-snapshots -DrepositoryId=my-repo-snapshots -Dfile=target/my-enforcer-maven-plugin-1.0.0-SNAPSHOT.jar -DpomFile=pom.xml
```

## Spring Boot 

This is a little cheatsheet about [Spring Boot](https://spring.io/projects/spring-boot).

### Configure ROOT log level by REST
```
curl -X "POST" "http://localhost:8080/manage/loggers/ROOT" \
  -H "Content-Type: application/json; charset=utf-8" -d $'{ "configuredLevel": "INFO" }'
```



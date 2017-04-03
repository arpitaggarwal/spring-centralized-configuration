# Steps to start an application

### Start Config Server

Move to directory `config-server` and run following command:

```
mvn spring-boot:run
```

Above command will start the config server at http://localhost:8888

### Start Rest Service

Move to directory `rest-service` and run following command:

```
mvn spring-boot:run -Dspring.profiles.active=dev
```

Above command will start the rest service loading `application-dev.properties` and accessible at http://localhost:8000/message

Similar to Dev, we can start the rest-service using `test` and `staging` properties as `mvn spring-boot:run -Dspring.profiles.active=test` and `mvn spring-boot:run -Dspring.profiles.active=staging` respectively.

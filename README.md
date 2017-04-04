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

### Refresh Rest Service Properties Values

To get changed value from the configuration server to the client we need to refresh the client with the following command:

```
curl -X POST http://localhost:8000/refresh
```

### Property File changes not reflecting in rest-service?

Whenever you modify any property file in `configstore` you have to make a git commit to reflect the changes in `config-server`, as:

```
git add .
git commit -m "property file update"
```

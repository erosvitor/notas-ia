
# Spring Boot Java project

## Remove unused files

- Remove the `static` and `template` folders from the `src/main/resource` directory.

## Add additional dependencies

- Add the following additional dependencies into `build.gradle` file.

```
implementation 'org.springdoc:springdoc-openapi-starter-webmvc-ui:3.0.3'
implementation 'org.owasp.encoder:encoder:1.4.0'
```

## Group dependencies

- Group the dependencies by purpose and add comment at the beginning of each group indicating its purpose. Follow the example below.

```
// WEB
implementation 'org.springframework.boot:spring-boot-starter-web'

// VALIDATION
implementation 'org.springframework.boot:spring-boot-starter-validation'

// DATABASE
implementation 'org.springframework.boot:spring-boot-starter-data-jpa'
```

## JaCoCo Plugin

- Add JaCoCo plugin.
- Create default configuration.
- Create configuration for code coverage with the following configurations:
  - element equals to class
  - limit mininum of 100%

## Add local configurations

- Add SpringDoc configurations into `application.properties` file.

```properties
# SpringDoc configurations
springdoc.swagger-ui.doc-expansion=none
springdoc.swagger-ui.operations-sorter=alpha
springdoc.swagger-ui.tags-sorter=alpha
```

- Add JPA configurations into `application.properties` file.

```properties
# JPA configurations
spring.datasource.driver-class-name=org.h2.Driver
spring.datasource.url=jdbc:h2:mem:DBXPTO;MODE=Oracle
spring.datasource.username=xpto
spring.datasource.password=
spring.jpa.hibernate.ddl-auto=none
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.default_schema=XPTO_ADM
spring.jpa.properties.hibernate.format_sql=true
spring.jpa.properties.hibernate.use_sql_comments=true
spring.jpa.properties.hibernate.generate_statistics=false
spring.h2.console.enable=true
spring.h2.console.path=/h2-console
```

## Add production configuration

- Create `application-prod.properties` file into `src/main/resources` folder and add following configurations.

```properties
# JPA configurations
spring.datasource.driver-class-name=oracle.jdbc.OracleDriver
spring.datasource.url=jdbc:oracle:thin:@//DBXPTO.INTRANET.COMPANYXPTO:1521/DBXPTO
spring.datasource.username=XPTO
spring.datasource.password=${DB_PASS}
spring.jpa.hibernate.ddl-auto=none
spring.jpa.show-sql=false
spring.jpa.properties.hibernate.default_schema=XPTO_ADM
spring.jpa.properties.hibernate.format_sql=false
spring.jpa.properties.hibernate.use_sql_comments=false
spring.jpa.properties.hibernate.generate_statistics=false
spring.h2.console.enable=false
```

## Create basic package structure

- Create following basic package structure.

```
  com/companyxpto/projectxpto
  |
  ├── config/
  ├── controller/
  ├── dao/
  ├── dto/
  ├── exception/
  │   └── handler/
  ├── mapper/
  ├── model/
  └── service/
```

## JPA mapping

- Create entities for following tables.

```
Users (
  id int auto_increment primary key,
  name varchar(60) not null,
  email varchar(80) not null,
  created_at timestamp default current_timestamp,
  updated_at timestamp
) 
```

- Add entities in exclusion list of code coverage rule.

## Data Access Object (DAOs)

- Create DAO for each entity created.

## Create services

- Create service for CRUD operations for each entity created.
- Create unit tests for each service created.

## Create controllers

- Create controller for each service created.
- Add swagger documentation.
- Create unit tests for controller created.

## OpenAPI

- Create an OpenAPI default configuration.

## H2 schema/data

- Create an H2 schema/data initializer (schema.sql/data.sql) for runnable local CRUD persistence.

## Run Gradle test command

- Run gradle clean test command to check if the project is working.

```shell
./gradlew clean test
```

## Let's do this step by step


# Create Spring Boot Java project

- Please make sure you have the following software installed on your system:

  - Java 21

## Check Java version

- Run following command in terminal and check the version of Java

```shell
java -version
```

## Download Spring Boot project template

- Run following command in terminal to download a Spring Boot project template

```shell
curl https://start.spring.io/starter.zip \
  -d type=gradle-project \
  -d language=java
  -d bootVersion=4.0.6 \
  -d groupId=com.companyxpto \
  -d artifactId=projectxpto \
  -d packageName=com.companyxpto.projectxpto \
  -d packaging=jar \
  -d javaVersion=21 \
  -d dependencies=web,data-jpa,h2,oracle,validation \
  -o starter.zip
```

## Unzip the downloaded file

- Run following command in terminal to unzip the downloaded file

```shell
unzip starter.zip -d ./projectxpto
```

## Remove the downloaded zip file

- Run following command in terminal to delete the downloaded zip file

```shell
rm -f starter.zip
```

## Change directory to the project root

- Run following command in terminal to change directory to the project root

```shell
cd projectxpto
```

## Remove unused files

- Remove the `static` and `template` folders from the `src/main/resource` directory

## Add additional dependencies

- Insert `springdoc-openapi-starter-webmvc-ui` dependency into `build.gradle` file

```
implementation 'org.springdoc:springdoc-openapi-starter-webmvc-ui:3.0.3'
```

## Add local configurations

- Insert SpringDoc configurations into `application.properties` file

```properties
# SpringDoc configurations
springdoc.swagger-ui.doc-expansion=none
springdoc.swagger-ui.operations-sorter=alpha
springdoc.swagger-ui.tags-sorter=alpha
```

- Insert JPA configurations into `application.properties` file

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

- Create `application-prod.properties` into `src/main/resources` folder and add following configurations

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

- Create following packages into `src/main/java/com/companyxpto/projectxpto`

```
  ├── application/
  │   ├── dto/
  │   ├── mapper/
  │   ├── service/
  │   └── usecase/
  ├── domain/
  │   ├── exception/
  │   ├── model/
  │   │   ├── entity/
  │   │   ├── enum/
  │   │   └── valueobject/
  │   ├── repository/  
  │   └── service/
  ├── infrastructure/
  │   ├── persistence/
  │   │   ├── dao/
  │   │   ├── entity/
  │   │   ├── mapper/
  │   │   └── provider/
  │   └── s3/
  ├── interfaces/
  │   ├── rest/
  │   │   ├── controller/
  │   │   ├── request/
  │   │   └── response/
```

## Run Gradle test command

- Run gradle clean test command to check if the project is working

```shell
./gradlew clean test
```

## Let's do this step by step

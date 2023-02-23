---
title: Deployment
---

All deploying files at `inlong-tubemq-manager` directory.

## Environment Preparation
- Install and start MySQL 5.7+
- Load `sql/apache_tube_manager.sql` through the command to complete the initialization of the table structure and basic data:

```` shell
# Create database and table with username and password:
mysql -uDB_USER -pDB_PASSWD < sql/apache_tube_manager.sql
````
  
## Configuration
- create `tubemanager` and account in MySQL.
- Add mysql information in conf/application.properties:

```ini
# mysql configuration for manager
spring.datasource.url=jdbc:mysql://mysql_ip:mysql_port/tubemanager
spring.datasource.username=mysql_username
spring.datasource.password=mysql_password
```

## Dependencies
- Please download [hibernate-commons-annotations-5.1.2.Final.jar](https://repo1.maven.org/maven2/org/hibernate/common/hibernate-commons-annotations/5.1.2.Final/hibernate-commons-annotations-5.1.2.Final.jar),
  [hibernate-core-5.6.7.Final.jar](https://repo1.maven.org/maven2/org/hibernate/hibernate-core/5.6.7.Final/hibernate-core-5.6.7.Final.jar), 
  [antlr-2.7.7.jar](https://repo1.maven.org/maven2/antlr/antlr/2.7.7/antlr-2.7.7.jar), 
  [jboss-logging-3.4.3.Final.jar](https://repo1.maven.org/maven2/org/jboss/logging/jboss-logging/3.4.3.Final/jboss-logging-3.4.3.Final.jar) and put it into `lib/` directory.

- If the backend database is MySQL, please download [mysql-connector-java-8.0.27.jar](https://repo1.maven.org/maven2/mysql/mysql-connector-java/8.0.27/mysql-connector-java-8.0.27.jar) and put it into `lib/` directory.

- If the backend database is PostgreSQL, there's no need for additional dependencies.

## Start

``` bash
$ bin/start-manager.sh 
```

## Register TubeMQ cluster

    vim bin/init-tube-cluster.sh

replace the parameters below
```
TUBE_MANAGER_IP=  
TUBE_MANAGER_PORT=   
TUBE_MASTER_IP=   
TUBE_MASTER_PORT=
TUBE_MASTER_WEB_PORT=
TUBE_MASTER_TOKEN=
```

then run：
```
sh bin/init-tube-cluster.sh
```

this will create a cluster with id = 1, note that this operation should not be executed repeatedly.
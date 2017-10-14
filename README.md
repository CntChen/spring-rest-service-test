# spring-rest-service-test-in-tomcat
learning java.
deploy spring boot application to tomcat.

fork form https://github.com/CntChen/spring-rest-service-test

## document
* howto-traditional-deployment
> https://docs.spring.io/spring-boot/docs/current/reference/html/howto-traditional-deployment.html

* How to Deploy a WAR File to Tomcat
> http://www.baeldung.com/tomcat-deploy-war

* Docker and Apache Tomcat
> http://trimc-devops.blogspot.com/2015/03/running-docker-applications-apache.html

## environment
```
maven 3.5.0
java 1.8.0_144
tomcat 9.0 with java 1.8.0_141
```

**warning:** the java version used by maven to generator war should be match tomcat's java version.

## deployment
* start tomcat
```bash
$ git clone https://github.com/CntChen/tomcat-test
$ cd tomcat-test
$ docker-compose -f docker-compose.yml up --build --force-recreate
```

* deploy
```
$ mvn tomcat7:deploy
```

* undeploy
```
$ mvn tomcat7:undeploy
```

* test
```bash
$ curl localhost:8080/sprint-rest-service-test/greeting
{"id":6,"content":"Hello, World!"}%
```

## EOF
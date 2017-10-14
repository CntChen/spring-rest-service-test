# spring-rest-service-test
learning java.

for war and tomcat deployment:
> https://github.com/CntChen/spring-rest-service-test/tree/war-tomcat

## environment
```bash
$ mvn -v
Apache Maven 3.5.0 (ff8f5e7444045639af65f6095c62210b5713f426; 2017-04-04T03:39:06+08:00)
Maven home: /usr/local/Cellar/maven/3.5.0/libexec
Java version: 9, vendor: Oracle Corporation
Java home: /Library/Java/JavaVirtualMachines/jdk-9.jdk/Contents/Home
Default locale: en_CN, platform encoding: UTF-8
OS name: "mac os x", version: "10.12.6", arch: "x86_64", family: "mac"
```

## start
* follow document:
> https://spring.io/guides/gs/rest-service/

* update maven package configulation
error when run `mvn package`:
```bash
[ERROR] Failed to execute goal org.apache.maven.plugins:maven-jar-plugin:2.6:jar (default-jar) on project spring-rest-service-test: Execution default-jar of goal org.apache.maven.plugins:maven-jar-plugin:2.6:jar failed: An API incompatibility was encountered while executing org.apache.maven.plugins:maven-jar-plugin:2.6:jar: java.lang.ExceptionInInitializerError: null
```

how to fix this:
> https://stackoverflow.com/questions/46353477/jdk9-and-maven-jar-plugin

add the following code to `pom.xml` inside `plugins` property:
```
<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-jar-plugin</artifactId>
    <version>3.0.2</version>
</plugin>
```

## run
* package
```
$ mvn package
```
and `target` folder is genarated.

* run
```
$ java -jar /target/spring-rest-service-test-0.1.0.jar
```

* test
```
$ curl localhost:8080/greeting
{"id":1,"content":"Hello, World!"}%
```

## add `./mvnw`
* add
```
$ mvn -N io.takari:maven:wrapper
```

* use
```
$ ./mvnw spring-boot:run
```

## EOF
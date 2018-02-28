FROM openjdk:9-jdk

VOLUME /tmp
ADD target/gs-rest-service-1.0-snapshot.jar gs-rest-service-1.0-snapshot.jar

ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","/gs-rest-service-1.0-snapshot.jar"]
EXPOSE 8080

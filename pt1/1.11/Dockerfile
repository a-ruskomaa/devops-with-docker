FROM openjdk:8-jdk-slim

EXPOSE 8080

WORKDIR /usr/src/app

COPY . .

RUN ./mvnw package

CMD [ "java", "-jar", "./target/docker-example-1.1.3.jar" ]
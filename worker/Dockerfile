FROM maven:3.5-jdk-8-alpine as builder

ENV MAVEN_OPTS="-Xmx4096m -XX:MaxPermSize=2048m"

WORKDIR /app

COPY pom.xml .
RUN mvn dependency:resolve

COPY src ./src
RUN mvn package

FROM openjdk:8-jre-alpine

WORKDIR /app

COPY --from=builder /app/target/worker-jar-with-dependencies.jar .

EXPOSE 80

CMD ["java", "-jar", "worker-jar-with-dependencies.jar"]


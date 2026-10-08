FROM maven:3.9-eclipse-temurin-17 AS build
WORKDIR /app
COPY . .
RUN mvn -q -pl event-api-service -am package -DskipTests
FROM eclipse-temurin:17-jre
WORKDIR /app
COPY --from=build /app/event-api-service/target/event-api-service-1.0.0.jar app.jar
ENTRYPOINT ["java","-jar","app.jar"]

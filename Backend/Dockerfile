# Use Maven image for building
FROM maven:3.9.6-eclipse-temurin-17 AS build

WORKDIR /app
COPY Backend /app
RUN mvn clean package -DskipTests

# Use a lightweight JDK runtime for running the application
FROM eclipse-temurin:17-jdk
WORKDIR /app
COPY --from=build /app/target/*.jar app.jar

EXPOSE 8080
CMD ["java", "-jar", "app.jar"]

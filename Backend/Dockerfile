# Use a Maven image that includes JDK 17
FROM maven:3.8.7-eclipse-temurin-17 AS build

# Set the working directory
WORKDIR /app

# Copy the Backend folder (which contains pom.xml and src/)
COPY Backend /app

# Build the Spring Boot project
RUN mvn clean install -DskipTests -Ddependency-check.skip=true

# Use a lightweight JDK runtime for running the application
FROM eclipse-temurin:17-jdk

# Set the working directory
WORKDIR /app

# Copy the built JAR file from the build stage
COPY --from=build /app/target/*.jar app.jar

# Expose port 8080
EXPOSE 8080

# Run the application
CMD ["java", "-jar", "app.jar"]

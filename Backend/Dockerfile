# Use a lightweight JDK image
FROM eclipse-temurin:17-jdk

# Set the working directory
WORKDIR /app

# Copy only the Backend folder (which contains pom.xml and src/)
COPY Backend /app

# Move into the correct directory
WORKDIR /app

# Build the Spring Boot project
RUN mvn clean package -DskipTests

# Expose port 8080
EXPOSE 8080

# Run the application
CMD ["java", "-jar", "/app/target/my-spring-project-0.0.1-SNAPSHOT.jar"]

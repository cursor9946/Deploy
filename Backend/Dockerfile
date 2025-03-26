# Use a lightweight JDK image
FROM eclipse-temurin:17-jdk

# Set the working directory
WORKDIR /app

# Copy only the Backend folder (which contains pom.xml and src/)
COPY Backend /app

# Move into the correct directory
WORKDIR /app

# Build the Spring Boot project
RUN mvn clean install  -DskipTests -Ddependency-check.skip=true

# Expose port 8080
EXPOSE 8080

# Run the application
CMD ["java", "-jar", "target/*.jar"]

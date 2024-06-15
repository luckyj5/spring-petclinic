# Dockerfile for Spring PetClinic application

FROM openjdk:17-jdk-slim

LABEL maintainer="Shubham Jain"

# Working directory
WORKDIR /app

# Copy the JAR file
COPY target/spring-petclinic-*-SNAPSHOT.jar app.jar

# Make port 8080 available
EXPOSE 8080

# Run the application 
ENTRYPOINT ["java", "-jar", "app.jar"]

# Command arguments
CMD ["--server.port=8080"]

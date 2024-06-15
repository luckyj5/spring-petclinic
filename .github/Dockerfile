# Dockerfile for Spring PetClinic application

FROM openjdk:17-jdk-slim

LABEL maintainer="Shubham Jain"

# Working directory
WORKDIR /app

# Copy the JAR file
COPY target/spring-petclinic-*-SNAPSHOT.jar app.jar

# Make port 8181 available
EXPOSE 8181

# Run the application 
ENTRYPOINT ["java", "-jar", "app.jar"]

# Command arguments
CMD ["--server.port=8181"]

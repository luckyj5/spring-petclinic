[![CI/CD Pipeline](https://github.com/luckyj5/spring-petclinic/actions/workflows/ci.yml/badge.svg)](https://github.com/luckyj5/spring-petclinic/actions/workflows/ci.yml)
# Spring PetClinic CI/CD Pipeline

This repository contains a GitHub Actions workflow for the Spring PetClinic project, including Docker packaging and integration with JFrog Artifactory. 

## Repository Structure

- **ci.yml:** Contains the Github Actions CI pipeline configuration defined in the `.github/workflows/ci.yml` file
- **Dockerfile:** Defines the Docker image configuration for the Spring Pet Clinic project defined in the `.github/DOckerfile`.
- **readme_cicd.md:** This file defined in `.github/readme_cicd.md`, explaining the project and how to run it.

## CI/CD Pipeline Flow

#### 1. Compile the Code
- The pipeline compiles the Spring Pet Clinic code using Maven.
- Maven dependencies are resolved to ensure all required dependencies are available.

#### 2. Run Tests
- After compiling the code, the pipeline runs tests to ensure the code functions as expected.
- Test results are generated and stored for review.

#### 3. Package the Project as a Runnable Docker Image
- Once tests pass successfully, the pipeline packages the project into a runnable Docker image.
- The Docker image is tagged with the version or tag specified in the pipeline.

#### 4. Push Docker image to Jfrog Artifactory
- Integrate JFrog Artifactory into the pipeline for artifact management and storage.


## How to Run the Project

### Prerequisites
- GitHub account and repository
- Docker installed [https://docs.docker.com/get-docker/]
- Maven installed [https://maven.apache.org/install.html]
- JFrog Artifactory account [https://jfrog.com/]

### Steps
1. Fork or clone the [Spring PetClinic repository](https://github.com/luckyj5/spring-petclinic).
   ```
   git clone <repo>
   cd spring-petclinic
   ```
2. Build the Docker image:
   ```
   docker build -t <docker-image> .
   ```
3. Run the Docker container:
   ```
   docker run -p 8080:8080 <docker-image>
   ```
4. Open your browser and navigate to `http://localhost:8080/` to access the Spring PetClinic application.


### Run the Pipeline

Make sure to add the Docker Registry and JFrog credentials (DOCKER_REGISTRY_URL, JF_USER, JFROG_ACCESS_TOKEN) to the GitHub repository secrets.

Push your changes to GitHub. The GitHub Actions pipeline will automatically run and perform the following steps:

1. Checkout the code.
2. Set up JDK 17.
3. Resolve dependencies and build the project using Maven.
4. Run the tests using Maven.
5. Log in to JFrog Artifactory Docker registry.
6. Build the Docker image.
7. Push the Docker image to JFrog Artifactory.
8. Save artifacts and cleanup

## Using the Runnable Docker Image

**Saving the Docker Image as a tar file**
   ```
   docker save -o spring-petclinic.tar <image>

   ```
**Loading and Running the Docker Image**

   ```
   docker load -i spring-petclinic.tar

   docker run -p 8080:8080 spring-petclinic
   ```

**Access the application**
   Open your browser and go to http://localhost:8080.


## Additional Information

- For more details on the Spring Pet Clinic project, refer to the official repository: [Spring Pet Clinic GitHub](https://github.com/spring-projects/spring-petclinic)
- Refer to the GitHub Actions documentation for more details on configuring workflows: [GitHub Actions Documentation](https://docs.github.com/en/actions)

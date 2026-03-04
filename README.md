# Flask API Docker CI/CD

![GitHub Actions](https://img.shields.io/badge/build-passing-brightgreen)
![Docker Hub](https://img.shields.io/badge/Docker%20Hub-ready-blue)

## Features
- 🚀 **Fast**: Quick API response times.
- 🔒 **Secure**: Implementing best practices for security.
- 📦 **Dockerized**: Fully containerized for easy deployment.
- 🔄 **Continuous Integration**: Automated testing with GitHub Actions.

## CI/CD Pipeline Overview
This project utilizes a CI/CD pipeline set up with GitHub Actions. Below is a breakdown of the key components:

### Dockerfile
The Dockerfile is responsible for creating a container image. It includes all necessary dependencies and configurations to run the Flask API.

### docker.yml Workflow
The `docker.yml` file defines the workflow for CI/CD. It includes steps for:
- Building the Docker image.
- Running tests on the API.
- Pushing the image to Docker Hub upon passing tests.

## Test Results
Tests are run automatically upon each commit. The results can be viewed in the Actions tab of the repository. Tests ensure that all features are working as expected before deployment.

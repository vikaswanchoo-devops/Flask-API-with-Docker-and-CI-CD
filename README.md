# FlaskAPI-Docker-CI-CD

## Features
- This project provides a Flask API application.
- Full CI/CD pipeline using GitHub Actions.
- Easy to setup and run via Docker.

## Steps to Run Locally
1. Clone the repository: `git clone https://github.com/vikaswanchoo-devops/FlaskAPI-Docker-CI-CD.git`
2. Navigate into the project directory: `cd FlaskAPI-Docker-CI-CD`
3. Build the Docker image: `docker build -t flaskapi .`
4. Run the Docker container: `docker run -p 5000:5000 flaskapi`

## Dockerfile
The Dockerfile is used to build the Docker image for the Flask application. It includes:  
- **Base Image**: The application starts from the official Python image.  
- **Working Directory**: Sets the working directory in the container.  
- **Dependencies**: Uses `requirements.txt` to install the necessary Python packages.  
- **Expose Port**: The application listens on port 5000.  
- **Entry Point**: Defines the command that runs the Flask application.

## docker.yml Workflow
The `docker.yml` file configures our GitHub Actions workflow for building and deploying the Docker image: 
- **Trigger**: The workflow is triggered on push to the main branch.  
- **Jobs**:  
  - Build the Docker image  
  - Log in to Docker Hub  
  - Push the image to Docker Hub  
- Each job consists of several steps to ensure the correct building and pushing of the image to the repository.

## Overall Repository Information
This repository demonstrates how to use Flask with Docker and GitHub Actions to implement a CI/CD pipeline. The primary purpose is to automate the build, test, and deployment process of the Flask application.

---

Documentation last updated: 2026-03-04 09:56:59 UTC
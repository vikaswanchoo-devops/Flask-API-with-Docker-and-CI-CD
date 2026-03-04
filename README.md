# FlaskAPI-Docker-CI-CD

## Project Overview
This project is a Flask API that is containerized using Docker and integrated with GitHub Actions for Continuous Integration (CI) and Continuous Deployment (CD).

## Dockerfile Explained
The `Dockerfile` in this repository sets up the environment for running the Flask API. Below are the key components:

1. **Base Image**: The Dockerfile starts with a base image that has Python pre-installed. This simplifies the image and ensures necessary packages are available.
   
   ```dockerfile
   FROM python:3.9
   ```

2. **Setting Working Directory**: We set `/app` as the working directory where our application will reside.
   
   ```dockerfile
   WORKDIR /app
   ```

3. **Copying Files**: The `COPY` instruction copies the necessary files from the local filesystem into the container's filesystem.
   
   ```dockerfile
   COPY requirements.txt .
   COPY . .
   ```

4. **Installing Dependencies**: With the `RUN` command, we install the required Python packages specified in `requirements.txt`.
   
   ```dockerfile
   RUN pip install --no-cache-dir -r requirements.txt
   ```

5. **Exposing Port**: The application runs on port 5000, so we expose this port to allow external access.
   
   ```dockerfile
   EXPOSE 5000
   ```

6. **Running the Application**: Finally, we define the command to run the Flask application.
   
   ```dockerfile
   CMD ["python", "app.py"]
   ```

## GitHub Actions CI/CD Workflow
The GitHub Actions workflow defines how the application is built and deployed:

- **Triggering Events**: The workflow is triggered on push events to the `main` branch and on pull requests.
 
- **Build Step**: The workflow checks out the code, sets up Python, installs dependencies, and builds the Docker image.

- **Testing**: Automated tests are run to ensure that the application behaves as expected.

- **Deployment**: If tests pass, the workflow deploys the application using Docker.

For a full understanding of the GitHub Actions workflow, please refer to the `.github/workflows/main.yml` file in this repository.

## Conclusion
This project showcases how to set up a Flask API with Docker and automate the CI/CD process using GitHub Actions.
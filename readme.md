# Simple Jenkins Pipeline for CI/CD

This project demonstrates how to set up a basic Jenkins pipeline to automate the building and deployment of an application using Jenkins and Docker.

### Objective

- Automate building, testing, and deploying an application.
- Use Jenkins to trigger pipeline runs on every code commit.
- Containerize the application using Docker and deploy it.

### Tools Used
* **Jenkins** - Automation server to run CI/CD pipelines.
* **Docker** - Container platform for building and deploying applications.

### Pipeline Overview

The Jenkins pipeline is defined in the ```Jenkinsfile``` located in the project repository. The pipeline includes the following stages:
1. **Build** - Build the Docker image of the application.
2. **Test** - Run any tests on the application ( can be customized ).
3. **Deploy** - Deploy the build Docker image to the target environment.

## Setup Instructions 
1. **Install Jenkins**
   * Install Jenkins locally or use a cloud-hosted Jenkins instance.
   * Ensure Jenkins has access to Docker on the build agents or server.
2. **Add Jenkinsfile to Project Repo**
   * The Jenkinsfile in this repo contains the pipeline script with build, test, and deploy stages.
   * This file defines all the steps Jenkins will execute automatically.
3. **Configure Jenkins Job**
   * Create a new pipeline job in Jenkins.
   * Connect it to your project repository (e.g., GitHub).

   * Point the job to use the Jenkinsfile from the repository.

   * Configure Jenkins to trigger the pipeline on each code commit (e.g., using GitHub webhooks or SCM polling).
4. **Run and Test the Pipeline**
   * Make changes to your application code and push to the repository.

   * Jenkins will automatically trigger the pipeline.

   * Monitor the build, test, and deploy stages on the Jenkins dashboard.

   * Verify the application is successfully deployed using Docker.

## Benefits
* Automates the deployment process.

* Ensures consistent and repeatable builds.

* Enables fast feedback by running tests early in the pipeline.

* Streamlines continuous integration and continuous delivery with Jenkins

------------------------------------------------------------
Feel free to customize the ```Jenkinsfile``` stages, tests, and deployment steps as per your project's specific needs.

This simple pipeline provides a solid foundation to learn DevOps practices using Jenkins and Docker. 

## Happy building and deploying!
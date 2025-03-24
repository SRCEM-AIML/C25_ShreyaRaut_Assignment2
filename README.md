Student Project – Multi-App Django Application
Overview
This is a Django-based multi-app project.

Framework: Django

Containerization: Docker

Automation: Jenkins

Deployment: Docker Hub

Project Structure
StudentProject/ - Main Django project folder

app1/ - Contains the homepage

app2/ - Contains a sample page

templates/ - Global templates for UI

static/ - Contains CSS for styling

Dockerfile - Defines how the project runs inside a container

Jenkinsfile - Automates the CI/CD pipeline

How to Run the Project Locally
1. Clone the Repository
Open a terminal and run the following command:
git clone https://github.com/SRCEM-AIML/C25_ShreyaRaut_Assignment2.git

Navigate into the project folder:
cd C25_ShreyaRaut_Assignment2

2. Run Using Docker
If you want to run the project inside a Docker container, follow these steps:

Build the Docker image:
docker build -t shreyaraut12/studentproject .

Run the container:
docker run -p 8000:8000 shreyaraut12/studentproject

Pull from Docker Hub
Instead of building manually, you can pull the prebuilt image:

Pull the image from Docker Hub:
docker pull shreyaraut12/studentproject:latest

Run the container:
docker run -p 8000:8000 shreyaraut12/studentproject

Your project will now be live on http://127.0.0.1:8000/.

Jenkins CI/CD Pipeline
The Jenkins pipeline automates the following steps:

Pulling code from GitHub

Building a Docker image

Pushing it to Docker Hub

To trigger the pipeline, push any changes to GitHub, and Jenkins will handle the deployment automatically.

Important Links
GitHub Repository: C25_ShreyaRaut_Assignment2

Docker Hub Image: shreyaraut12/studentproject

Conclusion
This project demonstrates a full CI/CD pipeline with Django, Docker, and Jenkins. It ensures that every code change is automatically built, tested, and deployed using best DevOps practices.



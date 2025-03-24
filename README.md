Student Project – Multi-App Django Application
Overview
This is a Django-based multi-app project demonstrating:

Framework: Django

Containerization: Docker

Automation: Jenkins

Deployment: Docker Hub

📁 Project Structure
graphql
Copy
Edit
StudentProject/   # Main Django project
│── app1/         # Contains the homepage
│── app2/         # Contains a sample page
│── templates/    # Global templates for UI
│── static/       # Contains CSS for styling
│── Dockerfile    # Defines the Docker container
│── Jenkinsfile   # Automates the CI/CD pipeline
🚀 How to Run the Project Locally
1️⃣ Clone the Repository
bash
Copy
Edit
git clone https://github.com/SRCEM-AIML/C25_ShreyaRaut_Assignment2.git  
cd C25_ShreyaRaut_Assignment2  
2️⃣ Run Using Docker
If you want to run the project inside a Docker container, use:

bash
Copy
Edit
docker build -t shreyaraut12/studentproject .  
docker run -p 8000:8000 shreyaraut12/studentproject  

📦 Pull from Docker Hub
Instead of building manually, you can pull the prebuilt image:

bash
Copy
Edit
docker pull shreyaraut12/studentproject:latest  
docker run -p 8000:8000 shreyaraut12/studentproject  
Your project will now be accessible at http://127.0.0.1:8000/.

⚙️ Jenkins CI/CD Pipeline
The Jenkins pipeline automates:

Pulling code from GitHub

Building a Docker image

Pushing it to Docker Hub

🛠 How to Trigger the Pipeline?
Make any changes to the project and push them to GitHub.

Jenkins will automatically pull, build, and deploy the latest version.

🔗 Important Links
GitHub Repository: C25_ShreyaRaut_Assignment2
Docker Hub Image: shreyaraut12/studentproject

📌 Conclusion
This project demonstrates a fully automated CI/CD pipeline with Django, Docker, and Jenkins, ensuring efficient deployment using best DevOps practices.



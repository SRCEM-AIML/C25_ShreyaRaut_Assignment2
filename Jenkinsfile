pipeline {
    agent any

    environment {
        // Docker image name (use your Docker Hub username and project name)
        DOCKER_IMAGE = 'shreyaraut12/studentproject' 
        
        // Docker Hub credentials ID stored in Jenkins
        DOCKER_CREDENTIALS = 'docker-hub-credentials' 
    }

    stages {
        // Clone the repository from GitHub
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/SRCEM-AIML/C25_ShreyaRaut_Assignment2.git'
            }
        }

        // Build the Docker image from the Dockerfile
        stage('Build Docker Image') {
            steps {
                script {
                    // Build the Docker image with the name stored in DOCKER_IMAGE
                    dockerImage = docker.build("${DOCKER_IMAGE}")
                }
            }
        }
stage('Test Docker') {
    steps {
        script {
            sh 'docker --version'  // This will check if Docker is accessible
        }
    }
}
        // Push the built Docker image to Docker Hub
        stage('Push to Docker Hub') {
            steps {
                script {
                    // Use the docker.withRegistry step to log in to Docker Hub with credentials and push the image
                    docker.withRegistry('https://index.docker.io/v1/', "${DOCKER_CREDENTIALS}") {
                        dockerImage.push('latest')  // Push the image with the 'latest' tag
                    }
                }
            }
        }
    }

    post {
        success {
            // If the pipeline succeeds
            echo '✅ Build and push successful!'
        }
        failure {
            // If the pipeline fails
            echo '❌ Build or push failed. Check the logs!'
        }
    }
}



pipeline {
    agent any

    environment {
        DOCKER_IMAGE = 'shreyaraut12/studentproject'  // Docker image name (must be lowercase)
        DOCKER_CREDENTIALS = 'docker-hub-credentials' // Ensure this exists in Jenkins credentials
    }

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/SRCEM-AIML/C25_ShreyaRaut_Assignment2.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    dockerImage = docker.build("${DOCKER_IMAGE}")
                }
            }
        }

        stage('Push to Docker Hub') {
            steps {
                script {
                    docker.withRegistry('https://index.docker.io/v1/', DOCKER_CREDENTIALS) {
                        dockerImage.push('latest')
                    }
                }
            }
        }
    }

    post {
        success {
            echo '✅ Build and push successful!'
        }
        failure {
            echo '❌ Build or push failed. Check the logs!'
        }
    }
}


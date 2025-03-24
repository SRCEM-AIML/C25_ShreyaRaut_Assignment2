pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/SRCEM-AIML/C25_ShreyaRaut_Assignment2.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    try {
                        bat 'docker build -t shreyaraut12/studentproject .'
                    } catch (Exception e) {
                        error "Docker build failed: ${e}"
                    }
                }
            }
        }
        stage('Push to Docker Hub') {
            steps {
                script {
                    try {
                        withDockerRegistry(credentialsId: 'docker-hub-credentials') {
                            bat 'docker push shreyaraut12/studentproject'
                        }
                    } catch (Exception e) {
                        error "Docker push failed: ${e}"
                    }
                }
            }
        }
    }
}
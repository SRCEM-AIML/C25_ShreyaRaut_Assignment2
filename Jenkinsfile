pipeline {
    agent any
    
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/SRCEM-AIML/C25_ShreyaRaut_Assignment2.git'
            }
        }
        
        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t shreyaraut12/studentproject .'
                }
            }
        }
        
        stage('Push to Docker Hub') {
            steps {
                script {
                    docker.withRegistry('https://index.docker.io/v1/', 'Studentproject') {
                        sh 'docker push shreyaraut12/studentproject'
                    }
                }
            }
        }
    }
}
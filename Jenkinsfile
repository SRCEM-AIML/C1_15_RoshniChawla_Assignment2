pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/SRCEM-AIML/C1_15_RoshniChawla_Assignment2.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    try {
                        sh 'docker build -t roshnichawla/studentproject .'
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
                            sh 'docker push roshnichawla/studentproject'
                        }
                    } catch (Exception e) {
                        error "Docker push failed: ${e}"
                    }
                }
            }
        }
    }
}

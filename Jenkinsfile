pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/SRCEM-AIML/C1_15_RoshniChawla_Assignment2.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t roshnichawla/studentproject .'
            }
        }
        stage('Push to Docker Hub') {
            steps {
                withDockerRegistry(credentialsId: 'docker-hub-credentials') {
                    sh 'docker push roshnichawla/studentproject'
                }
            }
        }
    }
}
git commit -m "Added Jenkinsfile and other project files"

git add .
git commit -m "initial commit"

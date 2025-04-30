pipeline {
    agent any

    stages {
        stage('Clone from GitHub') {
            steps {
                git 'https://github.com/Shcherbinin-Aleksei/PEt_1.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    dockerImage = docker.build("pet_project_app")
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    sh 'docker rm -f pet_app || true'
                    sh 'docker run -d --rm --name pet_app -p 5000:5000 pet_project_app'
                }
            }
        }
    }

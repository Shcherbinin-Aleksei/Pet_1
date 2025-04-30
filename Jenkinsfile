pipeline {
    agent any

    stages {
        stage('Clean Workspace') {
            steps {
                deleteDir()
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t pet_project_app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker rm -f pet_app || true'
                sh 'docker run -d --rm --name pet_app -p 5000:5000 pet_project_app'
            }
        }
    }
}

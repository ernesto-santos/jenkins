pipeline {
    agent none
    stages {
        stage('Building the Docker Image') {
            agent any
            steps {
                sh 'docker build -t ubuntu-nginx-tito:latest .'
            }
        }
    }
}

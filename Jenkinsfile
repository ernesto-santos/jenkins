pipeline {
    agent none
    stages {
        stage('Building the Docker Image') {
            agent any
            steps {
                sh 'docker build -t ubuntu-nginx-tito:$BUILD_NUMBER .'
            }
        }
        stage('Inspecting the built Image') {
            agent any
            steps {
                sh 'docker image inspect ubuntu-nginx-tito:$BUILD_NUMBER'
            }
        }
        stage('Running a container from the built Image') {
            agent any
            steps {
                sh 'docker run -d -p 80:80 --name ubuntu-nginx-$BUILD_NUMBER ubuntu-nginx-tito:$BUILD_NUMBER'
            }
        }
    }
}

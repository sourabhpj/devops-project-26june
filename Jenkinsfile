pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build docker image') {
            steps {
                sh 'docker build -t sourabh-image .'
            }
        }
        stage('Deploy docker imge') {
            steps {
                sh 'docker stop sourabh-container || true'
                sh 'docker rm sourabh-container || true'
                sh 'docker run -d container --name sourabh-container -p 80:80 sourabh-image'
            }
        }
    }

}
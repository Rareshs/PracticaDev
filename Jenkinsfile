pipeline {
    agent any
    environment {
        dockerhub=credentials('docker-hub-token')
    }
    stages {
        stage('checkout') {
            steps {
                checkout scm
            }
        }
        stage('build') {
            steps {
                sh 'make demo-app-build'
            }
        }
    }
}

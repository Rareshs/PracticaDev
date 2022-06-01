pipeline {
    agent any
    environment {
        dockerhub=credentials('Docker')
    }
    stages {
        stage('checkout') {
            steps {
                checkout scm
            }
        }
        stage('build') {
            steps {
                bat 'make demo-app-build'
            }
        }
        stage('push') {
            steps {
                // sh "env"
                bat "docker logout"
                bat "echo $dockerhub_PSW | docker login -u $dockerhub_USR --password-stdin docker.io"
                bat 'make demo-app-push'
            }
        }
        stage('test') {
            steps {
                bat "echo Executing testing stage..."
            }
        }
        stage('deploy') {
            steps {
                bat "echo Executing deployment stage..."
            }
        }
    }
}
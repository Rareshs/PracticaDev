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
                sh 'make pregatit-demo-app-python'
            }
        }
        stage('push') {
            steps {
                // sh "env"
                sh "docker logout"
                sh "echo $dockerhub_PSW | docker login -u $dockerhub_USR --password-stdin docker.io"
                sh 'make pregatit-demo-app-python'
            }
        }
        stage('test') {
            steps {
                sh "echo Executing testing stage..."
            }
        }
        stage('deploy') {
            steps {
                sh "echo Executing deployment stage..."
            }
        }
    }
}
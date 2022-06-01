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
                sh 'echo building the app'
            }
        }
        stage('push') {
            steps {
                // sh "env"
                sh 'echo pushing the app'
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
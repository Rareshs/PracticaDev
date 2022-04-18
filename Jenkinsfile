pipeline {
    agent { 
        evniroment{
            docker-hubcredentials('docker')
        docker { image 'python:3.10.1-alpine' } 
    }
    stages {
        stage('build') {
            steps {
                sh 'make demo-app-build'
            }
        }
    stages {
        stage('push') {
            steps {
                sh "echo $dockerhub_PSW | docker login -u $dockerhub_USER --password-stdin
                sh 'make demo-app-push'
        }
    }
}

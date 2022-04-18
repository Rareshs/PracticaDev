pipeline {
    agent { 
        evniroment{
            dockerhub=credentials('docker')
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
                sh "env"
                sh "echo $dockerhub_PSW | docker login -u $dockerhub_USR --password-stdin"
                sh 'make demo-app-push'
            }
        }
    }
}

pipeline {
    agent any 
        evniroment{
            dockerhub=credentials('docker')
        } 
    stages{
        stage('checkout') {
            steps{
                checkout scm
            }
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

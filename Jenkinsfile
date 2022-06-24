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
                sh 'make demo-app-build'
            }
        }
        stage('push') {
            steps {
                // sh "env"
                sh "docker logout"
                sh "echo $dockerhub_PSW | docker login -u $dockerhub_USR --password-stdin docker.io"
                sh 'make demo-app-push'
            }
        }
        stage('test') {
            steps {
                sh "echo Executing testing stage..."
            }
        }
        stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "k8/controllers/app-deployment.yaml", kubeconfigId: "config")
        }
      }
    }
}
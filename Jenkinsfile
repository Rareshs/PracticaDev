pipeline {
    agent any
    environment {
        dockerhub=credentials('docker-hub-token')
    }
        }
        stage('build') {
            steps {
                sh 'make demo-app-build'
            }
        }
    }
}

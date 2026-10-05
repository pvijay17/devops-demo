pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh './mvnw clean package'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t devops-demo:1.0 .'
            }
        }
    }

    post {
        success {
            echo 'Build and Docker image creation successful!'
        }

        failure {
            echo 'Pipeline failed. Check the Jenkins console output.'
        }
    }
}
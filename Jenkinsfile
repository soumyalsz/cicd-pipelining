pipeline {
    agent any
    environment {
        DOCKER_HUB_USER = 'your-dockerhub-username'
        IMAGE_NAME      = 'enterprise-api-service'
        IMAGE_TAG       = "${BUILD_NUMBER}"
    }
    stages {
        stage('Code Checkout') {
            steps {
                echo 'Pulling latest code from GitHub...'
                checkout scm
            }
        }
        stage('Static Linting Check') {
            steps {
                echo 'Simulating code quality gates and syntax analysis...'
                sh 'echo "Syntax validation passed successfully."'
            }
        }
        stage('Build Docker Image') {
            steps {
                echo 'Triggering multi-stage Docker build process...'
                sh "docker build -t ${DOCKER_HUB_USER}/${IMAGE_NAME}:${IMAGE_TAG} ."
                sh "docker build -t ${DOCKER_HUB_USER}/${IMAGE_NAME}:latest ."
            }
        }
    }
}

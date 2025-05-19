pipeline {
    agent any

    environment {
        COMPOSE_PROJECT_NAME = 'ci-cd-jenkins-docker'
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/manasjia/ci-cd-jenkins-docker.git', branch: 'main'
            }
        }

        stage('Docker Compose Build') {
            steps {
                echo "Building Docker images using Compose..."
                sh 'docker compose build'
            }
        }

        stage('Docker Compose Up') {
            steps {
                echo "Bringing up containers using Compose..."
                sh 'docker compose up -d'
            }
        }
    }

    post {
        success {
            echo "Pipeline executed successfully!"
        }
        failure {
            echo "Pipeline failed. Please check logs."
        }
    }
}


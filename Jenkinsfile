pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Cloning source code...'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building application...'
                // If using npm, Maven, etc., insert your build commands here
                // Example: sh 'npm install'
            }
        }

        stage('Docker Build') {
            steps {
                echo 'Building Docker image...'
                sh '/usr/local/bin/docker build -t keisha841/fems-backend:latest .'
            }
        }

        stage('Docker Push') {
            steps {
                echo 'Pushing Docker image to Docker Hub...'
                sh '/usr/local/bin/docker push keisha841/fems-backend:latest'
            }
        }
    }
}

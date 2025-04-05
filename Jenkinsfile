pipeline {
    agent any
    environment {
        PATH = "/usr/local/bin:$PATH"
    }
    stages {
        stage('Checkout') {
            steps {
                echo 'Cloning source code...'
                // checkout scm
            }
        }
        stage('Build') {
            steps {
                echo 'Building application...'
            }
        }
        stage('Docker Build') {
            steps {
                echo 'Building Docker image...'
                sh 'docker build -t keisha841/fems-backend:latest .'
            }
        }
        stage('Docker Push') {
            steps {
                echo 'Pushing Docker image...'
                sh 'docker push keisha841/fems-backend:latest'
            }
        }
    }
}

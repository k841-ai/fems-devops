pipeline {
    agent any
    environment {
        PATH = "/usr/local/bin:/usr/bin:/bin:$PATH"
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
                sh '/usr/local/bin/docker build -t keisha841/fems-backend:latest .'
            }
        }

        stage('Docker Push') {
            steps {
                echo 'Pushing Docker image...'
                withCredentials([usernamePassword(credentialsId: 'docker-hub-creds', usernameVariable: 'DOCKER_USER', passwordVariable: 'DOCKER_PASS')]) {
                    sh """
                        echo "$DOCKER_PASS" | /usr/local/bin/docker login -u "$DOCKER_USER" --password-stdin
                        /usr/local/bin/docker push keisha841/fems-backend:latest
                    """
                }
            }
        }
    }
    post {
        always {
            echo 'Pipeline completed.'
        }
    }
}

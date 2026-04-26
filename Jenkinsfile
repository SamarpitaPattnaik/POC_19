pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "yourdockerhub/nodejs-cicd-app"
        DOCKER_TAG = "${BUILD_NUMBER}"
        EC2_HOST = "ec2-user@<your-ec2-ip>"
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/your-username/nodejs-cicd-app.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh "docker build -t $DOCKER_IMAGE:$DOCKER_TAG ."
            }
        }

        stage('Push Docker Image') {
            steps {
                echo "Configure Docker credentials in Jenkins"
            }
        }

        stage('Deploy to EC2') {
            steps {
                echo "Configure SSH and deployment"
            }
        }
    }
}

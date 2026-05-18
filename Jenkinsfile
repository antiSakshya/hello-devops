pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/antiSakshya/hello-devops.git'
            }
        }

        stage('Build') {
            steps {
                sh 'chmod +x mvnw'
                sh './mvnw clean package -DskipTests'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t hello-devops .'
            }
        }

    }
}
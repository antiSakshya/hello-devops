pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git branch: 'main', url: 'https://github.com/YOUR_USERNAME/hello-devops.git'
            }
        }

        stage('Build App') {
            steps {
                sh './mvnw clean package -DskipTests'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t hello-devops .'
            }
        }

        stage('Docker Run Test') {
            steps {
                sh 'docker run -d -p 8081:8080 hello-devops'
            }
        }
    }
}
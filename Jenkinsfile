pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/Setthaphong47/web-simple.git' // แก้ตรงนี้
            }
        }
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t my-web-cicd .'
            }
        }
        stage('Run Container') {
            steps {
                bat 'docker rm -f my-web || true'
                bat 'docker run -d --name my-web -p 8888:80 my-web-cicd'
            }
        }
    }
}
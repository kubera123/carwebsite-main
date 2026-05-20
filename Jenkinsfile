pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                echo 'Cloning Repository'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t carwebsite .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker rm -f carweb || true'
                sh 'docker run -d -p 8081:80 --name carweb carwebsite'
            }
        }
    }
}

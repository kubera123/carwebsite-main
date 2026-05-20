pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git branch: 'main',
                url: 'https://github.com/kubera123/carwebsite-main.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t carwebsite .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 8081:80 --name carweb carwebsite'
            }
        }
    }
}

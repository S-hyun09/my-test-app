pipeline {
    agent any
    stages {
        stage('Build Docker') {
            steps {
                sh 'docker build -t test-app:latest .'
            }
        }
        stage('Run Docker') {
            steps {
                sh 'docker rm -f test-app || true'
                sh 'docker run -d -p 5000:5000 --name test-app test-app:latest'
            }
        }
    }
}

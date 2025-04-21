pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t jenkins-node-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker rm -f jenkins-node-app || true'
                sh 'docker run -d -p 3000:3000 --name jenkins-node-app jenkins-node-app'
            }
        }
    }
}

pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/Misbah01118/jenkins-nodejs-app.git'
            }
        }

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
                sh 'docker run -d -p 3000:3000 --name jenkins-node-app jenkins-node-app || true'
            }
        }
    }
}

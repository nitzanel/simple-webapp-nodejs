pipeline {
    agent {
        label 'nino'
    }

    stages {
        stage('Clean') {
            steps {
                cleanWs()
            }
        }
        stage('Clone') {
            steps {
                git 'https://github.com/nitzanel/simple-webapp-nodejs.git'
            }
        }
        stage('Build') {
            steps {
                nodejs('nodejs') {
                    sh 'npm install'
                }
            }
        }
        stage('Test') {
            steps {
                nodejs('nodejs') {
                    sh 'npm test'
                }
            }
        }
    }
}

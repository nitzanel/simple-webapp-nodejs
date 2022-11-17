pipeline {
    agent {
        label 'nino'
    }

    options { skipDefaultCheckout() }
    stages {
        stage('Clean') {
            steps {
                cleanWs()
            }
        }
        stage('Clone') {
            steps {
                sh "echo test!!!"
                checkout scm
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

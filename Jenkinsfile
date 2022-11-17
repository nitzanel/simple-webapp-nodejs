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
                sh 'echo test!!!'
                checkout scm
            }
        }
        stage('Build') {
            steps {
                sh "docker build . -f Dockerfile -t nino:${BUILD_ID}"
                sh 'docker images'
            }
        }
        stage('Run') {
            steps {
                sh "docker run -itd -p 3000:3000 --name nino-${BUILD_ID} nino:${BUILD_ID} "
            }
    }
}
}

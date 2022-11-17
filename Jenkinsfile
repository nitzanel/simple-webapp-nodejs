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
                sh "docker images list -a"
                //sh "docker run -it nino:${BUILD_ID}"
            }
        }
    }
}

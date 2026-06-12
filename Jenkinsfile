pipeline {
agent any

stages {

    stage('Checkout') {
        steps {
            echo 'Fetching latest code from GitHub'
        }
    }

    stage('Build Docker Image') {
        steps {
            sh 'docker build -t calculator .'
        }
    }

    stage('Deploy Container') {
        steps {
            sh 'docker rm -f calculator-container || true'
            sh 'docker run -d -p 5000:80 --name calculator-container calculator'
        }
    }
}


}

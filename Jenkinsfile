pipeline {
    agent {
        docker {image 'jenkinsci/blueocean'}
    }
    stages {
        stage('Build') {
            steps {
                sh 'make'
            }
        }
    }
}

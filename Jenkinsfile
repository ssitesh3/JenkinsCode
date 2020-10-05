pipeline {
    agent none 
    stages {
        stage('Build') { 
            agent {
                docker {
                    image 'blueocean'
                }
            }
            steps {
                sh 'make'
            }
        }
    }
}

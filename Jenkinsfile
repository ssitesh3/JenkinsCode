pipeline {
    agent none 
    stages {
        stage('Build') { 
            agent {
                docker {
                    image 'jenkinsci/blueocean' 
                }
            }
            steps {
                sh 'make'
            }
        }
    }
}

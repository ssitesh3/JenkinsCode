pipeline {
    agent none 
    stages {
        stage('Build') { 
            
            agent {
                docker {
                    image 'lbeschastny/jenkins-build-essential' ' 
                }
            }
            steps {
                sh 'make'
            }
            
        }
    }
}

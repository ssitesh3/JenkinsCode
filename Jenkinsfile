pipeline {
    agent any 
    stages {
        stage('Build') { 
            agent {
                docker {
                    image 'lbeschastny/jenkins-build-essential' 
                }
            }
            steps {
                sh 'make'
            }
            steps {
                sh './testBin'
            }
        }
    }
}

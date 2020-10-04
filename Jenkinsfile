pipeline {
    agent none 
    stages {
        stage('Build') { 
            agent {
                docker {
                    image 'ubuntu' 
                }
            }
            steps {
                sh 'make'
            }
        }
    }
}

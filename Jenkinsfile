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
                sh './testBin'
            }
        stage('Test') {
            steps{
                
                sh cppcheck Jenkinsfile
            }
        }
    }
}

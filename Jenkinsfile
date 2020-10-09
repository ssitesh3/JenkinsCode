pipeline {
    agent any 
    stages {
        stage('Build') { 
            steps {
                agent {
                    docker {
                        image 'lbeschastny/jenkins-build-essential' 
                    }
            }
                sh 'make'
                sh './testBin'
            }
            stage('Test') {
                steps{
                    sh cppcheck JenkinsCode
                }
            }
        }
    }
}

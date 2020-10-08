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
                sh cppcheck --xml --xml-version=2 SOURCE_DIRECTORY 2> cppcheck.xml
            }
        }
    }
}
